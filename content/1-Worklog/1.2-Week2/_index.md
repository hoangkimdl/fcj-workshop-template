
---
title: "Week 2 Worklog"
date: 2026-10-12
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

- Learn about AWS Support and its role in providing technical, account, and billing assistance during the management and operation of AWS services.
- Understand the four AWS Support plans: Basic, Business Support+, Enterprise Support, and Unified Operations, including their features, support channels, service levels, and response times.
- Understand the three main types of AWS Support requests: Account and Billing Support, Service Limit Increase, and Technical Support.
- Learn how to access AWS Support, manage support plans, create Support Cases, select appropriate severity levels, and monitor submitted requests through AWS Support Center.
- Understand AWS Identity and Access Management (IAM) and its role in managing user identities, access permissions, and security within an AWS account.
- Learn about the main IAM components, including IAM User, IAM Group, IAM Policy, and IAM Role, and understand how to organize users and manage permissions according to the Principle of Least Privilege.
- Gain practical knowledge and experience in creating and managing IAM Groups, IAM Users, and IAM Roles, configuring access policies, and performing role switching (Switch Role) through the AWS Management Console.
- Develop practical skills in handling AWS Support requests and managing IAM access permissions while following security best practices and avoiding unnecessary AWS service costs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study the fundamentals of AWS Support and understand its role in providing account, billing, and technical assistance to AWS customers.<br>- Learn about the four AWS Support plans and their main features:<br>&nbsp;&nbsp;+ Basic: Provides basic account and billing assistance, AWS Support Forums, AWS Health Dashboard, and access to AWS documentation and guidance resources.<br>&nbsp;&nbsp;+ Business Support+: Provides 24/7 access to Cloud Support Engineers, unlimited support cases, AWS Trusted Advisor checks, AWS Support API, and third-party software support.<br>&nbsp;&nbsp;+ Enterprise Support: Includes Business Support+ features, Technical Account Manager (TAM), Concierge Support Team, Infrastructure Event Management, Well-Architected Reviews, and operational guidance.<br>&nbsp;&nbsp;+ Unified Operations: Includes Enterprise Support features and AWS Managed Services, proactive monitoring, incident management, change management, patch management, backup, and disaster recovery support.<br>- Compare the support plans in terms of service availability, support channels, additional features, and response times.<br>- Learn about the three main types of AWS Support requests:<br>&nbsp;&nbsp;+ Account and Billing Support: Assistance with account and billing-related issues.<br>&nbsp;&nbsp;+ Service Limit Increase: Requests to increase AWS service quotas.<br>&nbsp;&nbsp;+ Technical Support: Assistance with technical issues.<br>- Understand which types of support requests are available under the Basic plan and which require an upgraded support plan.<br>- Become familiar with AWS Support Center and learn how to access support services through the AWS Management Console.<br>- Learn how to change support plans through the Manage Support Plan section.<br>- Understand the additional monthly costs that may arise when upgrading from the Basic plan to paid support plans. | 12/10/2026 | 12/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 3 | - Study AWS Support request management and understand how AWS Support Center is used to create, manage, and track Support Cases.<br>- Learn how to identify the appropriate support request type for different issues:<br>&nbsp;&nbsp;+ Account and Billing Support: Handles issues related to invoices, payments, account verification, account information changes, and tax-related questions.<br>&nbsp;&nbsp;+ Service Limit Increase: Allows customers to request increases to default AWS service quotas according to their resource requirements.<br>&nbsp;&nbsp;+ Technical Support: Provides technical assistance for AWS services and third-party applications running on AWS, depending on the subscribed support plan.<br>- Learn about the severity levels used when submitting technical support requests:<br>&nbsp;&nbsp;+ General Guidance: General development questions or feature requests.<br>&nbsp;&nbsp;+ System Impaired: Non-critical application functionality is affected or not operating normally.<br>&nbsp;&nbsp;+ Production System Impaired: Important functionality of a production system is impaired or degraded.<br>&nbsp;&nbsp;+ Production System Down: Important production system functionality is unavailable.<br>&nbsp;&nbsp;+ Business-Critical System Down: Critical system functionality is unavailable, potentially causing serious disruption to business operations.<br>- Learn about the initial response times associated with different severity levels and applicable support plans.<br>- Study how to provide a clear subject, detailed issue description, relevant attachments, and required account information when creating a Support Case.<br>- Understand the importance of selecting an appropriate severity level and avoiding the disclosure of sensitive information such as passwords and AWS Access Keys.<br>- Learn how to monitor submitted requests through Support Cases and respond to additional questions from the AWS Support team. | 13/10/2026 | 13/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 4 | - **Practice:** Explore the process of creating and submitting AWS Support requests through AWS Support Center.<br>&nbsp;&nbsp;+ Access AWS Support Center through the AWS Management Console.<br>&nbsp;&nbsp;+ Select Create case to start a new support request.<br>&nbsp;&nbsp;+ Choose Account and Billing Support for an invoice-related support scenario.<br>&nbsp;&nbsp;+ Select Account and billing as the support category.<br>&nbsp;&nbsp;+ Select Invoice as the service and Question About My Invoice as the issue type.<br>&nbsp;&nbsp;+ Select General question as the severity level for an invoice inquiry scenario.<br>&nbsp;&nbsp;+ Enter a clear subject and provide a detailed description of the issue.<br>&nbsp;&nbsp;+ Navigate to Billing and Cost Management → Bills → Invoices to locate and download the required invoice.<br>&nbsp;&nbsp;+ Attach the relevant invoice and provide the corresponding Invoice ID.<br>&nbsp;&nbsp;+ Select Web under Contact us and review the request information before submission.<br>&nbsp;&nbsp;+ Submit the support request and learn how to access Support Cases to review its details and status.<br>- **Practice:** Explore the severity level selection process and compare expected response times across different support plans.<br>&nbsp;&nbsp;+ Identify the appropriate severity level based on the impact of an issue.<br>&nbsp;&nbsp;+ Distinguish between general guidance requests, impaired systems, production system interruptions, and business-critical system outages.<br>&nbsp;&nbsp;+ Review the support channels and response time commitments associated with each support plan.<br>- Learn how to change support plans and recognize the additional monthly costs that may arise from using paid support options.<br>- Understand how to provide complete information when submitting support requests, monitor case updates, and respond to additional information requests from AWS Support.<br>- Review security precautions when submitting support requests and ensure that passwords, Access Keys, and other sensitive authentication information are not disclosed. | 14/10/2026 | 14/10/2026 | [AWS Support - Request Support](https://000009.awsfcaj.com/) |
| 5 | - Study the fundamentals of AWS Identity and Access Management (IAM) and understand its role in managing identities, authentication, and access permissions for AWS resources.<br>- Learn about the main IAM components:<br>&nbsp;&nbsp;+ IAM User: Represents an individual user or service identity within an AWS account.<br>&nbsp;&nbsp;+ IAM Group: Organizes multiple IAM Users to manage access permissions centrally.<br>&nbsp;&nbsp;+ IAM Policy: A JSON-based document that defines which actions and resources users or roles are allowed or denied access to.<br>&nbsp;&nbsp;+ IAM Role: Provides temporary access permissions to trusted entities through the AssumeRole mechanism.<br>- Understand the differences between IAM Users, IAM Groups, IAM Policies, and IAM Roles.<br>- Learn how to attach IAM Policies to Users, Groups, and Roles to control access permissions.<br>- Study AWS Managed Policies and Customer Managed Policies.<br>- Understand the Principle of Least Privilege and Role-Based Access Control (RBAC).<br>- Learn about Trust Policies, Permission Policies, temporary security credentials, and the role of IAM Roles in secure access management.<br>- Study security best practices, including limiting root user access, creating individual IAM Users, and regularly reviewing assigned permissions. | 15/10/2026 | 15/10/2026 | [AWS IAM - Access Control](https://000002.awsfcaj.com/) |
| 6 | - **Practice:** Create and configure IAM Groups and IAM Users through the AWS Management Console.<br>&nbsp;&nbsp;+ Access the IAM service through the AWS Management Console.<br>&nbsp;&nbsp;+ Create an AdminGroup to centrally manage users with administrative permissions.<br>&nbsp;&nbsp;+ Attach the AdministratorAccess policy to AdminGroup according to the workshop instructions.<br>&nbsp;&nbsp;+ Create an IAM User named AdminUser and configure AWS Management Console access.<br>&nbsp;&nbsp;+ Add AdminUser to AdminGroup so that the user inherits the group's permissions.<br>&nbsp;&nbsp;+ Access the IAM User sign-in URL and log in using the AdminUser credentials.<br>- **Practice:** Create and configure an IAM Role and an OperatorUser.<br>&nbsp;&nbsp;+ Create an Admin Role with an appropriate trusted entity and administrative permissions.<br>&nbsp;&nbsp;+ Create an IAM User named OperatorUser and configure permissions allowing the user to perform the AssumeRole operation.<br>&nbsp;&nbsp;+ Configure the Trust Policy to specify which identities are allowed to assume the role.<br>&nbsp;&nbsp;+ Configure the Permission Policy to allow OperatorUser to perform the AssumeRole operation.<br>&nbsp;&nbsp;+ Sign in to the AWS Management Console using the OperatorUser credentials.<br>&nbsp;&nbsp;+ Perform Switch Role to assume the previously created Admin Role.<br>&nbsp;&nbsp;+ Verify the assumed role and check the permissions available during the session.<br>- Learn about temporary security credentials, IAM Role session duration, and how to monitor activities through AWS CloudTrail.<br>- Study the IAM cleanup procedure, including deleting IAM Users and IAM Groups created for the practical exercises and verifying that temporary resources have been removed. | 16/10/2026 | 16/10/2026 | [AWS IAM - Access Control](https://000002.awsfcaj.com/) |

### Week 2 Achievements:

- Gained an overall understanding of AWS Support and its role in providing account, billing, and technical assistance to AWS customers.

- Understood the four main AWS Support plans and their corresponding features:
  - **Basic:** Provides basic account and billing assistance, AWS Support Forums, AWS Health Dashboard, and access to AWS documentation and best-practice resources.
  - **Business Support+:** Provides 24/7 access to Cloud Support Engineers through phone, chat, and email; unlimited Support Cases; full AWS Trusted Advisor checks; AWS Support API; and third-party software support.
  - **Enterprise Support:** Includes Business Support+ features, Technical Account Manager (TAM), Concierge Support Team, Infrastructure Event Management, Well-Architected Reviews, operational guidance, and training resources.
  - **Unified Operations:** Provides Enterprise Support features combined with AWS Managed Services, proactive monitoring, incident management, change management, patch management, backup, disaster recovery, and security operations.

- Understood the differences between support plans in terms of available services, support channels, operational assistance, and initial response time commitments.

- Learned about the three main types of AWS Support requests:
  - **Account and Billing Support:** Provides assistance with account information, invoices, payments, account verification, account changes, and tax-related issues.
  - **Service Limit Increase:** Allows customers to request increases to default AWS service quotas according to their resource requirements.
  - **Technical Support:** Provides assistance with technical issues involving AWS services and third-party applications running on AWS, depending on the subscribed support plan.

- Understood the availability of different support request types under each support plan, particularly that Account and Billing Support and Service Limit Increase are available under the Basic plan, while Technical Support requires Business Support+ or a higher support plan according to the workshop instructions.

- Became familiar with AWS Support Center and understood its role in centrally creating, managing, and tracking support requests.

- Learned how to access AWS Support through the AWS Management Console and understood the process of changing support plans through the Manage Support Plan section.

- Recognized that upgrading from the Basic plan to paid support plans may increase monthly AWS account costs; therefore, support plans should be selected according to actual operational requirements.

- Learned about the five severity levels used when submitting technical support requests and their corresponding initial response times:
  - **General Guidance:** 24 hours for general development questions or feature requests.
  - **System Impaired:** 12 hours when non-critical application functionality is affected.
  - **Production System Impaired:** 4 hours when important production system functionality is impaired or degraded.
  - **Production System Down:** 1 hour when important production system functionality is unavailable.
  - **Business-Critical System Down:** 15 minutes when critical system functionality is unavailable and business operations are at serious risk.

- Understood that severity levels and response time commitments depend on the subscribed support plan. The Business-Critical System Down severity level is available under Enterprise Support and Unified Operations according to the workshop.

- Gained practical knowledge of the AWS Support request creation process through AWS Support Center, including:
  - Accessing the Support Center interface.
  - Selecting Create case to create a new support request.
  - Choosing the appropriate support request type.
  - Selecting the relevant service, issue category, and severity level.
  - Entering a clear subject and detailed issue description.
  - Attaching relevant supporting documents.
  - Providing the Invoice ID for invoice-related inquiries.
  - Selecting an appropriate contact method.
  - Reviewing and submitting the support request.
  - Accessing Support Cases to monitor request status and review submitted case details.

- Understood the invoice-related support request process, including how to locate and download invoices through Billing and Cost Management → Bills → Invoices and provide the necessary invoice information when requesting AWS assistance.

- Recognized the importance of providing complete and accurate information when creating Support Cases to help the AWS Support team understand issues and provide appropriate assistance.

- Learned how to monitor Support Case updates, respond to requests for additional information, and maintain communication with the AWS Support team until issues are addressed.

- Recognized the importance of protecting account information when communicating with AWS Support, particularly by avoiding the disclosure of passwords, Access Keys, and other sensitive authentication credentials.

- Gained an overall understanding of AWS Identity and Access Management (IAM) and its role in managing identities, authentication, authorization, and access control for AWS resources.

- Understood the functions and characteristics of the main IAM components, including:
  - **IAM User:** Represents an individual user or service identity within an AWS account, with corresponding security credentials and access permissions.
  - **IAM Group:** Organizes multiple IAM Users into groups to simplify permission management and centralized access control.
  - **IAM Policy:** A JSON-based document that defines which actions are allowed or denied on specific AWS resources.
  - **IAM Role:** Provides temporary security credentials and access permissions to trusted entities through the AssumeRole mechanism.

- Understood how IAM Groups simplify access management by allowing administrators to attach policies to groups instead of managing each user's permissions individually.

- Learned how IAM Policies control access to AWS services and resources through:
  - Defining allowed and denied actions.
  - Specifying resource-level access permissions.
  - Using AWS Managed Policies and Customer Managed Policies.
  - Applying access conditions based on tags, time, or location.
  - Following the Principle of Least Privilege.

- Distinguished between AWS Managed Policies and Customer Managed Policies and understood the importance of reviewing and testing policies through AWS Policy Simulator before applying them.

- Understood the role of IAM Roles in providing secure and temporary access permissions, including:
  - Trust Policies that specify which entities are allowed to assume a role.
  - Permission Policies that define which actions a role is allowed to perform.
  - Temporary security credentials with automatic expiration.
  - Cross-account access and service-to-service communication.
  - Role session duration and activity monitoring through CloudTrail.

- Gained practical knowledge and experience in creating and managing IAM Groups and IAM Users, including:
  - Creating an AdminGroup to centrally manage administrative permissions.
  - Attaching the AdministratorAccess policy to the administrative group in the practical environment.
  - Creating an IAM User named AdminUser.
  - Adding AdminUser to AdminGroup to inherit the group's permissions.
  - Configuring AWS Management Console access.
  - Using the IAM User sign-in URL to access AWS with the AdminUser account.

- Gained practical knowledge of creating IAM Roles and configuring role-based access control, including:
  - Creating an Admin Role with an appropriate trust relationship and access permissions.
  - Creating an OperatorUser for role-based access.
  - Configuring Trust Policies and Permission Policies.
  - Granting OperatorUser permission to perform the AssumeRole operation.
  - Signing in with the OperatorUser account and performing Switch Role.
  - Verifying access permissions after assuming the new role.

- Understood the benefits of using IAM Roles and temporary security credentials instead of sharing long-term credentials, particularly in terms of security, access control, and auditing.

- Learned how to clean up IAM resources created during practical exercises, including deleting temporary IAM Users and IAM Groups and verifying the cleanup process to maintain account security.
