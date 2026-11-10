---
title: "Blog 1"
date: 2026-11-10
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Designing a Resilient Multi-Region Event Processing System on AWS with Amazon EventBridge and Amazon Route 53

When an application is deployed in only one AWS Region, a major failure in that Region can disrupt the entire service. This is particularly concerning for event-driven systems, such as order processing, transaction updates, and user activity tracking, where high availability and data durability are essential.

To reduce these risks, organizations can implement a Multi-Region architecture in which one Region serves as the primary environment while another is prepared as a standby environment. By combining Amazon Route 53, Amazon API Gateway, Amazon EventBridge, Amazon SQS, AWS Lambda, and Amazon DynamoDB Global Tables, the system can redirect new requests to the standby Region when the primary Region experiences a failure.

## KEY POINTS TO UNDERSTAND

- **Multi-Region Architecture:** Deploying an application across multiple AWS Regions to improve availability and support disaster recovery.
- **Active-Passive:** Using the Primary Region to handle normal traffic while the Secondary Region serves as a standby environment.
- **Amazon Route 53:** Using Health Checks and Failover Routing Policy to monitor endpoints and route DNS queries to the appropriate Region.
- **Event-Driven Processing:** API Gateway receives requests, EventBridge routes events, SQS stores messages, and Lambda processes them.
- **DynamoDB Global Tables:** Maintaining data replicas across multiple AWS Regions through cross-Region replication.
- **Automatic Failover:** When the Primary Region fails to meet Health Check conditions, Route 53 can direct new DNS queries to the Secondary Region.
- **Data Consistency:** Considering replication latency, write conflicts, and duplicate message processing.

## 1. ARCHITECTURE OVERVIEW

**Multi-Region Architecture** is an application deployment model that uses multiple AWS Regions to reduce dependence on a single infrastructure location. This solution adopts an Active-Passive model consisting of:

- **Primary Region:** The main Region that receives and processes requests under normal operating conditions.
- **Secondary Region:** The standby Region, where the necessary components are pre-deployed to handle requests when the Primary Region experiences a failure.

In addition, the system uses **Event-Driven Architecture (EDA)**, which allows components to communicate through events rather than relying on direct interactions with one another. This approach separates request reception, event routing, and data processing while allowing individual components to scale independently.

## 2. AWS SERVICES AND THEIR ROLES

| AWS Service | Role |
|---|---|
| Amazon Route 53 | Manages DNS, monitors endpoint health, and performs Failover Routing. |
| Amazon API Gateway | Receives HTTP/HTTPS requests and forwards events to EventBridge. |
| Amazon EventBridge | Receives events through an Event Bus and routes them according to Event Rules. |
| Amazon SQS | Stores messages in queues until they are ready for processing. |
| AWS Lambda | Retrieves messages from SQS, processes business logic, and writes data to DynamoDB. |
| Amazon DynamoDB Global Tables | Replicates data across AWS Regions. |

**Amazon Route 53 – DNS Failover**

Route 53 uses Health Checks to monitor the availability of the endpoint in the Primary Region. When the endpoint no longer meets the health check conditions, the Failover Routing Policy allows Route 53 to return the Secondary Region's endpoint for new DNS queries.

**Amazon API Gateway and Amazon EventBridge**

API Gateway serves as the entry point for application requests. Through AWS Service Integration and the `PutEvents` API, API Gateway forwards event data to EventBridge. EventBridge receives the events, evaluates the configured Event Rules, and routes matching events to their designated targets.

**Amazon SQS and AWS Lambda**

SQS acts as an intermediate message queue, separating event reception from event processing. Lambda uses Event Source Mapping to retrieve messages from SQS in batches and execute the corresponding business logic.

**Amazon DynamoDB Global Tables**

Global Tables maintain replicas of the same DynamoDB table across multiple Regions. When data is written to one replica, the changes are replicated to the other replicas according to the configured consistency mode.

## 3. ARCHITECTURE AND OPERATIONAL FLOW

### 3.1. Overall Architecture

The solution deploys two independent event-processing pipelines across two AWS Regions. Each Region contains API Gateway, EventBridge, SQS, and Lambda components. Route 53 manages DNS routing, while DynamoDB Global Tables handle data replication between the two Regions.

**Architecture Diagram:**

*Figure 1. Multi-Region failover architecture using Amazon Route 53 and AWS serverless services.*

The main processing flow in each Region is:

`Amazon API Gateway → Amazon EventBridge → Amazon SQS → AWS Lambda → Amazon DynamoDB`

### 3.2. Normal Operating Conditions

When the Primary Region is operating normally, Route 53 resolves the domain name and prioritizes the endpoint of the primary environment.

Processing flow:

1. A user sends a request to the application domain name, and Route 53 resolves it to the Primary Region.
2. API Gateway receives the request and sends the event to EventBridge through the `PutEvents` API.
3. EventBridge evaluates the Event Rules and routes matching events to SQS.
4. Lambda retrieves messages from SQS in batches through Event Source Mapping.
5. Lambda processes the events and writes the results to the DynamoDB replica in the Primary Region.
6. DynamoDB Global Tables replicate the data changes to the replica in the Secondary Region.

### 3.3. When the Primary Region Experiences a Failure

When the Primary Region no longer meets the Health Check conditions, Route 53 updates its health status and applies the Failover Routing Policy.

Processing flow:

1. Route 53 Health Check detects that the Primary Region endpoint is unhealthy.
2. Route 53 switches to the Secondary Record for new DNS queries.
3. Users are routed to the API Gateway endpoint in the Secondary Region.
4. EventBridge receives and routes events to the SQS queue in the standby Region.
5. Lambda in the Secondary Region processes the messages and writes data to its local DynamoDB replica.

Because the necessary components have already been deployed, the Secondary Region can continue receiving and processing new requests without rebuilding the entire system.

### 3.4. When the Primary Region Recovers

When the Primary Region endpoint becomes healthy again and passes the Health Check, Route 53 can resume prioritizing the Primary Record for new DNS queries.

The process of directing traffic back to the primary environment is called **Failback**. However, users may continue using previously resolved DNS records for some time because of DNS caching and TTL settings. Therefore, the transition does not necessarily happen simultaneously across all devices.

## 4. DATA REPLICATION WITH DYNAMODB GLOBAL TABLES

DynamoDB Global Tables maintain data across multiple Regions, allowing applications to access local replicas when another Region experiences a failure.

Global Tables currently support two main consistency modes:

- **Multi-Region Eventual Consistency (MREC):** The default mode when no alternative consistency mode is specified. Data is replicated asynchronously across Regions, so there may be a delay before all replicas receive the latest changes.
- **Multi-Region Strong Consistency (MRSC):** Provides strong consistency across Regions, subject to AWS deployment requirements and limitations.

In the original AWS architecture example, the CloudFormation configuration creates replicas without explicitly specifying another consistency mode. Therefore, the default MREC mode is applied.

Several important considerations include:

- **Replication Lag:** The delay between the time data is written and the time it becomes available in another Region's replica.
- **Write Conflict:** Conflicts that may occur when the same record is updated simultaneously in multiple Regions.
- **Data Consistency:** Data across Regions may temporarily differ while replication is still in progress.
- **Recovery Point Objective (RPO):** The amount of data loss an application can tolerate in the event of a failure.

Therefore, it should not be assumed that every piece of data written to the Primary Region is immediately replicated to the Secondary Region.

## 5. DEPLOYMENT AND FAILOVER TESTING

To deploy the solution according to the AWS guide, the following prerequisites are required:

- An AWS account with permissions to manage the related services.
- AWS CLI and AWS SAM CLI installed and configured.
- A registered domain name and a Route 53 Hosted Zone.
- Appropriate ACM certificates in both Regions if Regional Custom Domains are used.
- Two selected AWS Regions designated as Primary and Secondary.

**General Deployment Process:**

1. **Deploy Primary Stack:** Create API Gateway, EventBridge, SQS, Lambda, Route 53 Health Check, Primary DNS Record, and the DynamoDB Global Table with the required replicas.
2. **Deploy Secondary Stack:** Create an independent processing pipeline in the standby Region and reference the existing DynamoDB Global Table.
3. **Verify Normal Operation:** Send an event to the Custom Domain and confirm that the request is received by the Primary Region.
4. **Simulate a Failure:** Make the Primary API Gateway endpoint fail its Health Check in the testing environment.
5. **Verify Failover:** Send another request and check whether the system has switched to the Secondary Region.
6. **Verify Data:** Review Lambda CloudWatch Logs and confirm that the record has been written to the DynamoDB replica in the Secondary Region.
7. **Restore the Primary Region:** Restore the API Gateway Stage and Base Path Mapping, then verify that Route 53 can prioritize the Primary Region again.

**Example of Sending a Test Event:**

```bash
curl -X POST https://api.example.com \
  -H "Content-Type: application/json" \
  -d '{
    "Detail": {
      "IsHelloWorldExample": "true"
    },
    "DetailType": "POSTED",
    "Source": "demo.event"
  }' -v
```

According to the AWS example, the HTTP response includes an `X-Region` header that identifies the Region handling the request. Under normal conditions, the result indicates the Primary Region. After a successful Failover, the result indicates the Secondary Region.

**Note:** With the example Health Check configuration using a 30-second interval and a Failure Threshold of 3, the failure detection threshold is approximately 90 seconds. However, the actual failover time also depends on DNS TTL and DNS Resolver caching.

## 6. BENEFITS AND IMPORTANT CONSIDERATIONS

**Benefits:**

- **Improved Availability:** Reduces dependence on a single AWS Region.
- **Disaster Recovery Support:** Provides a standby environment when the primary Region experiences a failure.
- **Reduced Component Coupling:** EventBridge and SQS help separate event reception from event processing.
- **Multi-Region Data Availability:** DynamoDB Global Tables replicate data across Regions.
- **Simplified Infrastructure Management:** AWS SAM and CloudFormation support infrastructure deployment through Infrastructure as Code.

**Important Considerations:**

- **DNS Failover Is Not Instantaneous:** DNS Resolvers may continue using previously cached DNS records until their TTL expires.
- **Appropriate Health Checks:** The monitored endpoint should accurately reflect the application's actual service availability.
- **Duplicate Message Processing:** Lambda and SQS may process a message more than once. Applications should implement Idempotent processing logic and consider using a Dead-Letter Queue.
- **Data Replication Monitoring:** ReplicationLatency should be monitored for Global Tables using MREC.
- **IAM Access Control:** Permissions should follow the Least Privilege principle.
- **Cost Monitoring:** Costs should account for API Gateway, Route 53 Health Checks, DynamoDB Global Tables, Lambda, SQS, CloudWatch Logs, and cross-Region data transfer.

After completing the testing process, it is recommended to delete the Secondary Stack first, followed by the Primary Stack, according to the AWS deployment guide. In particular, important data should be backed up because deleting the Primary Stack may also delete the Global Table and its stored data.

## 7. CONCLUSION

The Multi-Region Event-Driven Failover architecture, combining Amazon EventBridge and Amazon Route 53, is a solution that helps improve availability and disaster recovery capabilities for event-driven applications on AWS.

In this architecture, Route 53 monitors endpoint health and manages DNS routing between the Primary and Secondary Regions. API Gateway receives requests, EventBridge routes events, SQS stores messages, Lambda processes business logic, and DynamoDB Global Tables maintain data replicas across the deployed Regions.

This architecture demonstrates that building a standby system involves more than simply deploying an additional Region. The processing components, data replication mechanisms, and failover procedures must also be properly prepared and coordinated.

However, before applying this architecture in a production environment, organizations should evaluate RTO, RPO, DNS TTL, data replication latency, and duplicate message handling. These factors determine whether the architecture is suitable for the operational requirements of a particular application.

## REFERENCES

1. AWS Compute Blog – Multi-Region event-driven failover architecture with Amazon EventBridge and Route 53:  
   https://aws.amazon.com/blogs/compute/multi-region-event-driven-failover-architecture-with-amazon-eventbridge-and-route-53/

2. Amazon Route 53 – Failover Routing:  
   https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-failover.html

3. Amazon EventBridge – Rules in Amazon EventBridge:  
   https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html

4. Amazon EventBridge API – PutEvents:  
   https://docs.aws.amazon.com/eventbridge/latest/APIReference/API_PutEvents.html

5. AWS Lambda – Using Lambda with Amazon SQS:  
   https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html

6. Amazon DynamoDB – Global Tables:  
   https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GlobalTables.html

7. Amazon DynamoDB – How Global Tables Work:  
   https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/V2globaltables_HowItWorks.html

8. AWS CloudFormation – AWS SAM Transform:  
   https://docs.aws.amazon.com/AWSCloudFormation/latest/TemplateReference/transform-aws-serverless.html