
---
title: "Week 3 Worklog"
date: 2026-10-19
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

- Understand the overview of Amazon Virtual Private Cloud (Amazon VPC) and its role in building and managing isolated virtual network environments on AWS.
- Understand basic networking concepts, including IP addresses, CIDR, Availability Zones, and how to divide a network into Subnets to organize AWS resources.
- Learn about the functions and operations of VPC networking components, including Subnets, Route Tables, Internet Gateway (IGW), and NAT Gateway.
- Understand network security mechanisms in VPC through Security Groups and Network Access Control Lists (Network ACLs), and distinguish their scopes and operating mechanisms.
- Gain practical knowledge and experience in creating VPCs, configuring Subnets, Internet Gateways, Route Tables, Security Groups, and VPC Flow Logs.
- Learn how to deploy Amazon EC2 Instances in Public and Private Subnets, establish SSH connections, configure NAT Gateways, and verify network connectivity.
- Become familiar with AWS network analysis and monitoring tools, including VPC Resource Map, VPC Reachability Analyzer, AWS Systems Manager Session Manager, and Amazon CloudWatch.
- Understand AWS Site-to-Site VPN and the principles of establishing secure network connectivity between an On-premises environment and Amazon VPC through encrypted VPN tunnels.
- Gain practical experience in configuring Virtual Private Gateway (VGW), Customer Gateway (CGW), VPN Connection, and Libreswan software to establish Site-to-Site VPN connectivity.
- Understand the procedures for monitoring VPN Tunnels, customizing connection parameters, troubleshooting connectivity issues, and cleaning up AWS resources to minimize unexpected costs.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study the overview of Amazon Virtual Private Cloud (Amazon VPC) and its role in creating isolated virtual network environments on AWS.<br>- Learn about VPC network architecture and its basic concepts:<br>&nbsp;&nbsp;+ VPC: An isolated virtual network in AWS that allows users to control network configurations and deploy resources.<br>&nbsp;&nbsp;+ CIDR: The range of IP addresses allocated to a VPC and its Subnets.<br>&nbsp;&nbsp;+ Availability Zone (AZ): An independent location within an AWS Region that supports high availability for deployed resources.<br>- Learn about different types of Subnets:<br>&nbsp;&nbsp;+ Public Subnet: A Subnet with a route to the Internet through an Internet Gateway.<br>&nbsp;&nbsp;+ Private Subnet: A Subnet without a direct route to an Internet Gateway.<br>&nbsp;&nbsp;+ VPN-only Subnet: A Subnet configured with routes to a Virtual Private Gateway for VPN connectivity.<br>- Study Route Tables and their routing components:<br>&nbsp;&nbsp;+ Destination: The destination IP address or network range of traffic.<br>&nbsp;&nbsp;+ Target: The gateway or network component to which traffic is forwarded.<br>- Learn about Internet Gateway (IGW), its function in connecting a VPC to the Internet, and how to configure IGW routes in a Route Table.<br>- Understand NAT Gateway and how it allows resources in Private Subnets to initiate outbound Internet connections without allowing the Internet to initiate direct connections to those resources.<br>- Distinguish between NAT Gateway and NAT Instance.<br>- Study Multi-AZ network architecture and the benefits of distributing resources across multiple Availability Zones to improve availability. | 19/10/2026 | 19/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 3 | - Study network security mechanisms in Amazon VPC:<br>&nbsp;&nbsp;+ Security Group: A virtual firewall that controls inbound and outbound traffic at the Network Interface or associated resource level.<br>&nbsp;&nbsp;+ Network ACL (NACL): A network traffic control mechanism applied at the Subnet level.<br>- Understand the differences between Security Groups and Network ACLs in terms of scope and operating mechanisms:<br>&nbsp;&nbsp;+ Security Groups are Stateful, meaning response traffic for permitted connections is automatically allowed.<br>&nbsp;&nbsp;+ Network ACLs are Stateless, requiring rules for both inbound and outbound traffic.<br>- Learn about Inbound Rules and Outbound Rules, including how to specify protocols, Port Ranges, and Source/Destination addresses when configuring security rules.<br>- Become familiar with VPC Resource Map to visualize relationships between VPCs, Subnets, Route Tables, Internet Gateways, and related network components.<br>- **Practice:** Build an Amazon VPC network environment using the AWS Management Console.<br>&nbsp;&nbsp;+ Access the VPC service and create a Custom VPC named ASG.<br>&nbsp;&nbsp;+ Configure the IPv4 CIDR block `10.10.0.0/16` for the VPC.<br>&nbsp;&nbsp;+ Enable Enable DNS Hostnames and Enable DNS Resolution in VPC Settings.<br>&nbsp;&nbsp;+ Create Public and Private Subnets in the selected Availability Zones.<br>&nbsp;&nbsp;+ Create an Internet Gateway and attach it to the ASG VPC.<br>&nbsp;&nbsp;+ Create a Route Table for the Public Subnet and configure the default route `0.0.0.0/0` to the Internet Gateway.<br>&nbsp;&nbsp;+ Associate the Subnets with their appropriate Route Tables.<br>&nbsp;&nbsp;+ Create a Security Group and configure Inbound Rules and Outbound Rules according to connectivity requirements.<br>&nbsp;&nbsp;+ Learn how to configure Network ACLs to control traffic at the Subnet level.<br>&nbsp;&nbsp;+ Enable VPC Flow Logs to record and monitor IP traffic flowing to and from Network Interfaces.<br>- Review the VPC Resource Map to verify the network structure and relationships between components after configuration. | 20/10/2026 | 20/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 4 | - **Practice:** Deploy Amazon EC2 Instances in the created VPC environment.<br>&nbsp;&nbsp;+ Access the Amazon EC2 service and select Launch instances.<br>&nbsp;&nbsp;+ Create Public and Private EC2 Instances according to the workshop architecture.<br>&nbsp;&nbsp;+ Select an appropriate Amazon Machine Image (AMI) and Instance Type.<br>&nbsp;&nbsp;+ Configure Key Pairs, VPCs, Subnets, and Security Groups for each EC2 Instance.<br>&nbsp;&nbsp;+ Check the public IP addresses, private IP addresses, and operational status of the EC2 Instances.<br>- **Practice:** Verify connectivity to EC2 Instances.<br>&nbsp;&nbsp;+ Establish SSH connections to EC2 Instances using Visual Studio Code with the Remote - SSH extension, following the workshop instructions.<br>&nbsp;&nbsp;+ Verify connectivity between EC2 Instances and other components within the VPC.<br>&nbsp;&nbsp;+ Test Internet connectivity for resources configured in Public Subnets.<br>- **Practice:** Create and configure a NAT Gateway.<br>&nbsp;&nbsp;+ Allocate an Elastic IP Address for the NAT Gateway.<br>&nbsp;&nbsp;+ Create a Public NAT Gateway in the appropriate Public Subnet.<br>&nbsp;&nbsp;+ Associate the NAT Gateway with the allocated Elastic IP Address.<br>&nbsp;&nbsp;+ Configure the Private Subnet Route Table with the default route `0.0.0.0/0` pointing to the NAT Gateway.<br>&nbsp;&nbsp;+ Verify outbound Internet connectivity from the EC2 Instance in the Private Subnet.<br>- Study VPC Reachability Analyzer and how to use it to analyze network paths, examine Security Group and Network ACL configurations, and identify potential causes of connectivity failures.<br>- Learn about EC2 Instance Connect Endpoint as an additional EC2 connection method (optional content).<br>- Study AWS Systems Manager Session Manager and how to securely access EC2 Instances through a browser without requiring SSH Keys or opening inbound SSH ports.<br>- Learn about CloudWatch Monitoring & Alerting and how to monitor EC2, NAT Gateway, VPN Connection, and VPC Flow Logs metrics.<br>- Understand how to configure CloudWatch alarms to monitor resources and detect network connectivity issues. | 21/10/2026 | 21/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 5 | - Study the overview of AWS Site-to-Site VPN and its purpose in establishing secure network connectivity between an On-premises environment and Amazon VPC.<br>- Learn about Site-to-Site VPN architecture and the functions of its main components:<br>&nbsp;&nbsp;+ Virtual Private Gateway (VGW): The AWS-side VPN gateway attached to a VPC.<br>&nbsp;&nbsp;+ Customer Gateway (CGW): Represents the VPN device or software on the customer network side.<br>&nbsp;&nbsp;+ VPN Connection: The VPN connection established between a Virtual Private Gateway and a Customer Gateway.<br>&nbsp;&nbsp;+ VPN Tunnel: An encrypted communication tunnel used to securely transfer data between two network environments.<br>- **Practice:** Build a simulated Branch Office environment for VPN connectivity.<br>&nbsp;&nbsp;+ Create a separate VPC named ASG VPN with the IPv4 CIDR block `10.11.0.0/16`.<br>&nbsp;&nbsp;+ Create a Public Subnet and configure an Internet Gateway for the VPN environment.<br>&nbsp;&nbsp;+ Create a Route Table and configure appropriate network routes.<br>&nbsp;&nbsp;+ Create a Security Group that allows the necessary connections for VPN, SSH, and connectivity testing according to the workshop instructions.<br>&nbsp;&nbsp;+ Launch an EC2 Instance in the Public Subnet to act as the Customer Gateway environment.<br>&nbsp;&nbsp;+ Check the public IP address of the EC2 Instance used as the Customer Gateway.<br>- **Practice:** Create AWS Site-to-Site VPN components.<br>&nbsp;&nbsp;+ Create a Virtual Private Gateway named VPN Gateway and attach it to the target VPC.<br>&nbsp;&nbsp;+ Create a Customer Gateway using the public IP address of the EC2 Customer Gateway.<br>&nbsp;&nbsp;+ Configure the BGP ASN according to the instructions, using the default value of 65000 for the static routing scenario.<br>&nbsp;&nbsp;+ Create a VPN Connection and select the previously created Virtual Private Gateway and Customer Gateway.<br>&nbsp;&nbsp;+ Select Static Routing and specify the network range `10.11.0.0/16` of the simulated Customer Gateway environment.<br>&nbsp;&nbsp;+ Check the VPN Connection status and wait until the resource reaches the Available state. | 22/10/2026 | 22/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |
| 6 | - **Practice:** Configure the Customer Gateway and establish VPN Tunnels.<br>&nbsp;&nbsp;+ Access the created VPN Connection in the VPC Console.<br>&nbsp;&nbsp;+ Download the VPN configuration file for the Customer Gateway device.<br>&nbsp;&nbsp;+ Select Vendor and Platform as OpenSwan, Software as OpenSwan 2.6.38+, and IKE version as IKEv1 according to the workshop instructions.<br>&nbsp;&nbsp;+ Establish an SSH connection to the EC2 Instance acting as the Customer Gateway.<br>&nbsp;&nbsp;+ Install and configure Libreswan on the EC2 Instance according to the instructions.<br>&nbsp;&nbsp;+ Check and modify the IPsec configuration in `/etc/ipsec.conf` when necessary.<br>&nbsp;&nbsp;+ Configure IP Forwarding and the necessary network parameters on the Customer Gateway.<br>&nbsp;&nbsp;+ Configure the VPN Tunnel using the configuration file provided by AWS.<br>&nbsp;&nbsp;+ Check the VPN Tunnel status and verify connectivity between the AWS network and the simulated Branch Office environment.<br>- Learn how to customize VPN Tunnel parameters through the AWS VPC Console:<br>&nbsp;&nbsp;+ Dead Peer Detection (DPD) Timeout.<br>&nbsp;&nbsp;+ IKE versions (IKEv1/IKEv2).<br>&nbsp;&nbsp;+ Encryption Algorithms.<br>&nbsp;&nbsp;+ Integrity Algorithms.<br>&nbsp;&nbsp;+ Diffie-Hellman (DH) Groups.<br>- Learn how to enable VPN Tunnel Activity Logs and use Amazon CloudWatch Logs to monitor VPN activities, connection events, and authentication information.<br>- Study the VPN Troubleshooting Guide and learn how to check Tunnel status, IKE/IPsec configurations, routing, IP Forwarding, and system logs to troubleshoot connectivity issues.<br>- Explore alternative VPN configurations and the StrongSwan with Transit Gateway connectivity model as optional workshop extensions.<br>- Study Infrastructure as Code (IaC) Templates and the benefits of automating VPC deployment through infrastructure definition files.<br>- **Practice:** Review and clean up AWS resources created during the lab in the appropriate order:<br>&nbsp;&nbsp;+ Terminate the EC2 Instances created for the lab.<br>&nbsp;&nbsp;+ Delete NAT Gateways.<br>&nbsp;&nbsp;+ Release Elastic IP Addresses when they are no longer in use.<br>&nbsp;&nbsp;+ Delete VPC Endpoints if they were created.<br>&nbsp;&nbsp;+ Delete VPN Connections.<br>&nbsp;&nbsp;+ Detach and delete Virtual Private Gateways.<br>&nbsp;&nbsp;+ Delete Customer Gateways.<br>&nbsp;&nbsp;+ Delete the related VPCs after removing dependent resources.<br>- Verify that all resources have been properly cleaned up to minimize unexpected AWS charges. | 23/10/2026 | 23/10/2026 | [Amazon VPC and AWS Site-to-Site VPN Workshop](https://000003.awsfcaj.com/) |

### Week 3 Achievements:

- Gained an overall understanding of Amazon Virtual Private Cloud (Amazon VPC) and its role in building isolated virtual network environments and managing AWS resources through user-defined network configurations.

- Understood basic networking architecture and IP addressing concepts in VPC, including:
  - **VPC:** A logically isolated virtual network environment within AWS.
  - **CIDR:** An IP address range used to define the network address space of a VPC and its Subnets.
  - **Availability Zone (AZ):** An independent location within an AWS Region that supports resource distribution and high availability.
  - **Subnet:** A subdivision of a VPC into smaller networks to organize and manage AWS resources.

- Distinguished different types of Subnets based on routing configurations and their purposes:
  - **Public Subnet:** Has a route to the Internet through an Internet Gateway.
  - **Private Subnet:** Does not have a direct route to an Internet Gateway but can use a NAT Gateway to initiate outbound Internet connections.
  - **VPN-only Subnet:** Configured with routes to a Virtual Private Gateway to communicate through a VPN connection.

- Understood the functions and operations of VPC routing components:
  - **Route Table:** Contains routing rules that determine how network traffic is forwarded based on Destination and Target.
  - **Internet Gateway (IGW):** Allows resources in a VPC to communicate with the Internet when configured with public IP addresses and appropriate routes.
  - **NAT Gateway:** Allows resources in Private Subnets to initiate outbound connections to the Internet or external services without allowing the Internet to initiate direct connections to those resources.

- Understood the differences between NAT Gateway and NAT Instance, as well as the role of NAT Gateway in allowing resources in Private Subnets to access the Internet through outbound connections.

- Understood Multi-AZ architecture and the benefits of deploying resources across multiple Availability Zones to improve availability and reduce the risk of service disruption when an AZ experiences a failure.

- Understood network security mechanisms in Amazon VPC, including:
  - **Security Group:** A virtual firewall that controls inbound and outbound traffic at the Network Interface or associated resource level and operates using a Stateful mechanism.
  - **Network ACL (NACL):** A network traffic control mechanism applied at the Subnet level that operates using a Stateless mechanism.
  - **Inbound Rules:** Rules that control incoming traffic to resources.
  - **Outbound Rules:** Rules that control outgoing traffic from resources.

- Distinguished Security Groups and Network ACLs in terms of their application scope, operating mechanisms, and security rule configurations, while understanding the importance of allowing only necessary connections.

- Became familiar with VPC Resource Map and learned how to use it to visualize relationships between VPCs, Subnets, Route Tables, Internet Gateways, and other network components in AWS.

- Understood the function of VPC Flow Logs in recording IP traffic information flowing to and from Network Interfaces, supporting security monitoring, traffic analysis, and network troubleshooting.

- Gained practical knowledge and experience in building an Amazon VPC environment, including:
  - Creating a Custom VPC named ASG with the IPv4 CIDR block `10.10.0.0/16`.
  - Enabling Enable DNS Hostnames and Enable DNS Resolution.
  - Creating Public and Private Subnets in selected Availability Zones.
  - Creating an Internet Gateway and attaching it to the VPC.
  - Creating Route Tables and configuring the default route `0.0.0.0/0` to the Internet Gateway for Public Subnets.
  - Associating Subnets with appropriate Route Tables.
  - Creating and configuring Security Groups with Inbound Rules and Outbound Rules.
  - Learning how to configure Network ACLs to control traffic at the Subnet level.
  - Enabling VPC Flow Logs to monitor network traffic.

- Gained practical knowledge and experience in deploying Amazon EC2 Instances, including:
  - Selecting appropriate Amazon Machine Images (AMIs) and Instance Types.
  - Configuring Key Pairs, VPCs, Subnets, and Security Groups.
  - Deploying EC2 Instances in Public and Private Subnets.
  - Checking EC2 Instance operational status, public IP addresses, and private IP addresses.
  - Establishing SSH connections to EC2 Instances through Visual Studio Code and the Remote - SSH extension.
  - Verifying connectivity between resources within the VPC environment.

- Understood how to deploy a NAT Gateway in a Public Subnet, allocate and associate an Elastic IP Address, and configure the Private Subnet Route Table to allow EC2 Instances to access the Internet through outbound connections.

- Became familiar with VPC Reachability Analyzer and learned how to use the tool to:
  - Analyze network paths between resources within a VPC.
  - Verify network connectivity based on current configurations.
  - Examine Security Group and Network ACL rules.
  - Identify configuration components that may affect network connectivity.

- Learned about EC2 Instance Connect Endpoint as an additional method of connecting to EC2 Instances without relying entirely on public IP addresses.

- Understood the function of AWS Systems Manager Session Manager in securely accessing and managing EC2 Instances through interactive sessions with auditing capabilities, without requiring SSH Keys or opening inbound SSH ports.

- Understood the role of Amazon CloudWatch in monitoring resources and network traffic, including:
  - Monitoring NAT Gateway metrics.
  - Monitoring VPN Tunnel status and data traffic.
  - Monitoring EC2 Instance performance, CPU, and memory metrics when corresponding metrics are available.
  - Monitoring VPC Flow Logs and security events.
  - Learning how to configure alarms when metrics exceed specified thresholds.

- Gained an overall understanding of AWS Site-to-Site VPN and how to establish secure network connectivity between an On-premises environment and Amazon VPC through encrypted VPN Tunnels.

- Understood the functions of the main components in Site-to-Site VPN architecture:
  - **Virtual Private Gateway (VGW):** The AWS-side VPN gateway attached to a VPC to establish VPN connectivity.
  - **Customer Gateway (CGW):** Represents the VPN device or software on the customer network side.
  - **VPN Connection:** Establishes connectivity between a Virtual Private Gateway and a Customer Gateway.
  - **VPN Tunnel:** An encrypted tunnel used to securely transfer data between two network environments.

- Gained practical experience in building a simulated Branch Office environment for VPN connectivity, including:
  - Creating a separate VPC named ASG VPN with the IPv4 CIDR block `10.11.0.0/16`.
  - Creating a Public Subnet and configuring an Internet Gateway.
  - Creating a Route Table and configuring the necessary network routes.
  - Creating a Security Group for VPN, SSH, and network connectivity testing.
  - Deploying an EC2 Instance in a Public Subnet to act as the Customer Gateway.
  - Checking the public IP address of the EC2 Instance.

- Gained practical experience in creating and configuring AWS Site-to-Site VPN components, including:
  - Creating a Virtual Private Gateway and attaching it to the target VPC.
  - Creating a Customer Gateway using the public IP address of the EC2 Customer Gateway.
  - Configuring the BGP ASN according to the workshop instructions, using the default value of 65000 in the static routing scenario.
  - Creating a VPN Connection between the Virtual Private Gateway and Customer Gateway.
  - Selecting Static Routing and specifying the network range `10.11.0.0/16` of the simulated Customer Gateway environment.
  - Checking the VPN Connection status and connection initialization process.

- Understood the process of downloading and using the VPN configuration file provided by AWS for the Customer Gateway, including:
  - Selecting Vendor and Platform as OpenSwan.
  - Selecting Software OpenSwan 2.6.38+.
  - Selecting IKEv1 according to the workshop instructions.
  - Using the configuration file as the basis for establishing IPsec on the EC2 Customer Gateway.

- Gained practical knowledge of installing and configuring Libreswan on the EC2 Customer Gateway, including:
  - Installing Libreswan on a suitable Linux environment.
  - Checking and configuring the `/etc/ipsec.conf` file.
  - Enabling IP Forwarding and configuring the necessary network parameters.
  - Configuring IPsec parameters based on the AWS-provided configuration file.
  - Checking VPN Tunnel status and verifying data transmission between the two networks.

- Understood how to customize VPN Tunnel parameters, including DPD Timeout, IKE versions, encryption algorithms, integrity algorithms, and Diffie-Hellman Groups.

- Became familiar with enabling VPN Tunnel Activity Logs and using Amazon CloudWatch Logs to monitor VPN Tunnel activities, connection events, and information required for troubleshooting.

- Understood the procedures for checking and troubleshooting Site-to-Site VPN connectivity issues, including:
  - Checking VPN Tunnel operational status.
  - Verifying Customer Gateway and VPN Connection configurations.
  - Checking IKE/IPsec parameters and authentication processes.
  - Verifying IP Forwarding and routing information between the two networks.
  - Examining network configurations and system logs to identify the causes of connectivity interruptions.

- Explored alternative VPN configurations and the StrongSwan with Transit Gateway connectivity model as optional workshop extensions.

- Understood Infrastructure as Code (IaC) and the benefits of managing and deploying AWS infrastructure through machine-readable definition files, including:
  - Reusing configurations to deploy consistent environments.
  - Managing versions and tracking infrastructure changes.
  - Automating deployment processes to reduce manual errors.
  - Recreating or cleaning up environments systematically.
  - Supporting standardized infrastructure and security configuration checks.

- Recognized the importance of cleaning up AWS resources after completing practical exercises, especially NAT Gateways, Elastic IP Addresses, EC2 Instances, and VPN Connections, as these resources may incur charges during usage.

- Understood the resource cleanup sequence recommended by the workshop to avoid dependency-related errors:
  - Terminate EC2 Instances.
  - Delete NAT Gateways.
  - Release Elastic IP Addresses.
  - Delete VPC Endpoints, if any.
  - Delete VPN Connections.
  - Detach and delete Virtual Private Gateways.
  - Delete Customer Gateways.
  - Delete VPCs last.

- Understood that properly reviewing and cleaning up AWS resources helps minimize unexpected charges while keeping the AWS account environment organized and manageable.
