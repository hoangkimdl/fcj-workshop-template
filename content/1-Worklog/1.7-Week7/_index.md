---
title: "Week 7 Worklog"
date: 2026-11-16
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Learn about Amazon Relational Database Service (Amazon RDS), its role as a managed relational database service on AWS Cloud, and its benefits, including automated backups, software updates, resource scaling, and improved availability.
- Learn about the database engines supported by Amazon RDS, including Amazon Aurora, MySQL, MariaDB, Oracle, Microsoft SQL Server, and PostgreSQL.
- Understand the essential components and features of Amazon RDS, such as DB Instances, DB Endpoints, DB Subnet Groups, Storage Options, Automated Backups, Manual Snapshots, Multi-AZ, and Read Replicas.
- Learn about database security mechanisms through Amazon VPC, Security Groups, IAM Policies, AWS KMS, and SSL/TLS Encryption.
- Practice building a network environment for Amazon RDS deployment by creating a VPC and configuring Public Subnets, Private Subnets, Security Groups, and DB Subnet Groups to control connectivity between the application server and the database.
- Practice launching an Amazon RDS Database Instance using MySQL, configuring database server specifications, storage capacity, credentials, Multi-AZ deployment options, and secure connectivity settings.
- Practice launching an Amazon EC2 Instance using Amazon Linux 2023, configuring Key Pairs and Security Groups, and connecting to the server through SSH using MobaXterm.
- Practice connecting from EC2 to Amazon RDS MySQL through the DB Endpoint and MySQL Command Line Client, using SQL commands to create databases and tables, insert records, and retrieve information.
- Practice deploying the AWS User Management application using Node.js on EC2, configuring the connection to Amazon RDS through the `.env` file, and using PM2 to manage application processes.
- Learn and practice Automated Backups, Database Snapshot management, and database restoration on Amazon RDS to protect data and support Disaster Recovery.
- Understand the procedures for checking, cleaning up, and deleting Amazon RDS, EC2, DB Subnet Group, and VPC resources after completing the Workshop to minimize unnecessary costs.

### Tasks to Be Completed During the Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | **Learn About Amazon RDS and Prepare the Network Environment Using Amazon VPC**<br><br> - Learn about Amazon Relational Database Service (Amazon RDS), a managed relational database service provided by AWS that allows users to deploy and operate databases on AWS Cloud.<br> - Understand the role of Amazon RDS in storing and processing structured data, particularly for applications that use relational database management systems and Online Transaction Processing (OLTP).<br> - Learn about the benefits of Amazon RDS, including automated backups, database software updates, patch management during Maintenance Windows, resource scaling, and high availability support.<br> - Learn about the database engines supported by Amazon RDS, including:<br>&nbsp;&nbsp;+ Amazon Aurora.<br>&nbsp;&nbsp;+ MySQL.<br>&nbsp;&nbsp;+ MariaDB.<br>&nbsp;&nbsp;+ Oracle.<br>&nbsp;&nbsp;+ Microsoft SQL Server.<br>&nbsp;&nbsp;+ PostgreSQL.<br> - Distinguish Amazon RDS from self-managed database deployments on EC2; understand that Amazon RDS is a managed service, meaning users do not have root access to the underlying EC2 host, except for certain supported database engines through Amazon RDS Custom.<br> - Learn about Amazon RDS management features, including DB Instance security, software updates, Automated Backups, resource scaling, Multi-AZ, and Read Replicas.<br> - Learn about Amazon RDS storage options:<br>&nbsp;&nbsp;+ General Purpose SSD (gp3/gp2): Provides cost-effective storage suitable for various database workloads.<br>&nbsp;&nbsp;+ Provisioned IOPS SSD (io1/io2): Suitable for systems with high read and write performance requirements.<br>&nbsp;&nbsp;+ Magnetic Storage: A legacy storage option with limited performance that is not recommended for new deployments.<br> - Learn about Amazon RDS High Availability and Disaster Recovery mechanisms, including Multi-AZ Deployment with synchronous replication, Read Replicas with asynchronous replication, and Global Databases for cross-region replication.<br> - Learn about Amazon RDS security mechanisms, such as data encryption at rest using AWS KMS, data encryption in transit using SSL/TLS, network isolation through VPC, and access control using IAM Policies.<br> - Learn about Amazon RDS scalability options, including storage capacity expansion and compute resource modification based on workload requirements.<br> - Learn about Automated Backups, which support Point-in-Time Recovery with a retention period of up to 35 days, and Manual DB Snapshots, which are retained until manually deleted.<br> - Access the AWS Management Console and open Amazon VPC to prepare the network environment for database deployment.<br> - Practice selecting Create VPC and choosing the VPC and more configuration to create a VPC environment along with the required networking components.<br> - Set the VPC name to `rds`, configure the IPv4 CIDR Block as `10.0.0.0/16`, and select Default Tenancy according to the Workshop instructions.<br> - Configure the network architecture with 2 Availability Zones, 2 Public Subnets, and 2 Private Subnets, with one Public Subnet and one Private Subnet in each Availability Zone.<br> - Do not create a NAT Gateway or VPC Endpoint during the practical exercise to minimize additional costs.<br> - Keep DNS Resolution and DNS Hostnames at their default settings, then complete the VPC creation process.<br> - Check the Subnets created within the VPC and configure Public Subnets by navigating to Subnets → selecting a Public Subnet → Actions → Edit subnet settings.<br> - Enable Enable auto-assign public IPv4 address for Public Subnets to support connections to EC2 Instances.<br> - Verify that Subnets intended for RDS deployment do not automatically assign Public IPv4 addresses, reducing the risk of direct public access to the database.<br> - Review the overall VPC configuration, Availability Zones, Public Subnets, and Private Subnets before proceeding with the creation of security components. | 16/11/2026 | 16/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Introduce](https://000005.awsfcaj.com/1-introduce/)<br>[Create a VPC](https://000005.awsfcaj.com/2-prerequiste/2.1-create-vpc/) |
| Tuesday | **Practice Configuring Security Groups, DB Subnet Groups, and Launching an Amazon RDS Database Instance**<br><br> - Learn about Security Groups and their role as Virtual Firewalls for controlling Inbound and Outbound traffic for EC2 Instances and RDS Database Instances.<br> - Access the EC2 Console, open Security Groups, and select Create security group to create a dedicated Security Group for EC2.<br> - Set the Security Group name to `ec2-sg`, provide the description `Security group for EC2 instances connecting to RDS`, and select the previously created VPC.<br> - Configure the Inbound Rules for `ec2-sg`, including:<br>&nbsp;&nbsp;+ SSH (22): Allow access only from My IP for Linux server administration.<br>&nbsp;&nbsp;+ HTTP (80): Allow access from Anywhere-IPv4 to support Web traffic.<br>&nbsp;&nbsp;+ HTTPS (443): Allow access from Anywhere-IPv4 to support secure Web connections.<br>&nbsp;&nbsp;+ Custom TCP (5000): Allow access from Anywhere-IPv4 to test the Node.js application.<br> - Review the Inbound Rules and complete the creation of the `ec2-sg` Security Group.<br> - Create a separate Security Group for Amazon RDS named `rds-sg`, provide the description `Security group for RDS MySQL database instances`, and select the same VPC.<br> - Configure the MySQL/Aurora (3306) Inbound Rule and select the `ec2-sg` Security Group as the source instead of allowing access from the entire Internet.<br> - Understand the benefits of using a Security Group as the source, ensuring that only EC2 Instances with the appropriate Security Group can connect to the database.<br> - Learn the principle of separating Security Groups between application servers and database servers to strengthen resource isolation and access control.<br> - Access Amazon RDS, select Subnet groups → Create DB Subnet Group to create a group of Subnets for database deployment.<br> - Set the DB Subnet Group name to `rds-subnet-group`, provide the description `Subnet group for RDS instances`, and select the previously created VPC.<br> - In the Add subnets section, select Subnets belonging to at least two different Availability Zones, preferably Private Subnets for RDS deployment.<br> - Complete the DB Subnet Group creation process and verify the associated Subnets to ensure that the configuration meets Multi-AZ deployment requirements.<br> - Access Amazon RDS, select Databases → Create database, and choose the Full configuration method instead of Easy create to customize database settings.<br> - Select MySQL as the Database Engine according to the Workshop instructions.<br> - Select the Production template and choose Multi-AZ DB instance deployment (2 instances) to explore high-availability database deployment.<br> - Set the DB Instance Identifier to `db-instance`, the Master Username to `admin`, and select Self managed under Credential Management.<br> - Configure a strong administrative password according to the Workshop requirements, confirm the password, and store the credentials securely for subsequent connection steps.<br> - Configure the Instance Class as `db.m5.large`, the Storage Type as General Purpose SSD (gp3), and the Allocated Storage as 20 GiB according to the Workshop instructions.<br> - In the Connectivity section, select Don't connect to an EC2 compute resource, use the previously created VPC, and select the `rds-subnet-group` DB Subnet Group.<br> - Set Public Access to No to prevent the database from being publicly accessible over the Internet.<br> - In the VPC Security Group section, select Choose existing and attach the `rds-sg` Security Group to the DB Instance.<br> - In Additional Configuration, set the Initial Database Name to `fcaj`, keep the remaining options at their default values, and complete the database creation process.<br> - Check the RDS Database Instance creation status and verify that the Database Instance becomes available after initialization is complete.<br> - Access Connectivity & security and select Endpoints to identify the DB Endpoint and Port used by applications to connect to the database.<br> - Learn how to view Logs & events to monitor database lifecycle events, operational information, and related logs.<br> - Access Maintenance & backups to explore maintenance schedules, pending software updates, and database backup information. | 17/11/2026 | 17/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Create Security Group](https://000005.awsfcaj.com/2-prerequiste/2.2-create-ec2-sg/)<br>[Create Database Subnet Group](https://000005.awsfcaj.com/2-prerequiste/2.3-create-rds-subnet-group/)<br>[Create RDS Database Instance](https://000005.awsfcaj.com/3-create-rds/) |
| Wednesday | **Practice Launching an Amazon EC2 Instance and Connecting to a Linux Server Through SSH**<br><br> - Learn about Amazon EC2 and its role in providing flexible computing capacity on AWS Cloud for application server deployment.<br> - Access the Amazon EC2 Console and select Launch instances to create a Linux server for connecting to Amazon RDS.<br> - Name the EC2 Instance `ec2-instance` and select the Amazon Linux 2023 AMI operating system under Quick Start.<br> - Configure the Instance Type as `t3.micro` according to the Workshop instructions and understand the importance of selecting an Instance Type suitable for application workload requirements.<br> - Practice creating a new Key Pair named `kp-linux`, selecting RSA as the Key Pair Type and `.pem` as the Private Key Format.<br> - Download the `kp-linux.pem` private key file to the personal computer and store it securely for SSH connections.<br> - In the Network Settings section, select the previously created VPC and a Public Subnet.<br> - Enable Auto-assign public IP so that the EC2 Instance receives a Public IPv4 address for connections from the personal computer.<br> - Select Select existing security group and attach the `ec2-sg` Security Group to the EC2 Instance.<br> - Review the AMI, Instance Type, Key Pair, VPC, Subnet, and Security Group before selecting Launch instance.<br> - Monitor the EC2 Instance launch process, wait until its status changes to Running, and check the Status Checks before connecting.<br> - Copy the Public IPv4 address of `ec2-instance` from the EC2 Console.<br> - Practice connecting to Amazon Linux 2023 through SSH using MobaXterm on a Windows computer.<br> - Create a New Session, select SSH, and configure Remote Host using the Public IPv4 address of the EC2 Instance.<br> - Set the username to `ec2-user`, the Port to 22, open Advanced SSH settings, and select Use private key to specify the downloaded `kp-linux.pem` file.<br> - Confirm the SSH connection and complete the login process to the Amazon Linux 2023 server.<br> - Inspect the Terminal environment on the EC2 Instance and become familiar with administering a Linux server through command-line operations.<br> - Understand the roles of Public Subnets, Public IPv4 addresses, Key Pairs, and Security Groups in establishing connections to EC2 Instances.<br> - Recognize the importance of protecting private keys and restricting SSH access to trusted IP addresses to strengthen server security. | 18/11/2026 | 18/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Launch EC2 Instance](https://000005.awsfcaj.com/4-create-ec2/) |
| Thursday | **Practice Connecting EC2 to Amazon RDS MySQL and Deploying the AWS User Management Application**<br><br> - Learn about the connection architecture between Amazon EC2 and Amazon RDS, in which EC2 acts as the application server while RDS stores and manages relational database data.<br> - Practice updating software packages on Amazon Linux 2023 using the `sudo dnf update -y` command before preparing the application deployment environment.<br> - Install Git using `sudo yum install git` and install the MySQL Command Line Client through the `mariadb105` package using `sudo dnf install mariadb105`.<br> - Verify the Git and MariaDB Client versions after installation using `git --version && mariadb --version`.<br> - Access Amazon RDS, open the `db-instance` Database Instance, and copy its DB Endpoint from Connectivity & security → Endpoints.<br> - Practice connecting to the database through the MySQL Command Line Client using `mysql -h [YOUR-RDS-ENDPOINT] -P 3306 -u admin -p`, replacing the Endpoint with the actual value and entering the configured Master User password.<br> - Learn the roles of MySQL connection parameters, including `-h` for the DB Endpoint, `-P` for Port 3306, and `-u` for the database administrator account.<br> - Use the SQL command `SHOW DATABASES;` to check the list of existing databases in RDS.<br> - Check whether the `fcaj` database exists; use `CREATE DATABASE IF NOT EXISTS fcaj;` if the database has not been created.<br> - Use the `USE fcaj;` command to select the database for subsequent operations.<br> - Practice creating a `user` table in the `fcaj` database using the SQL CREATE TABLE statement.<br> - Learn about the structure of the `user` table, including the fields `id`, `first_name`, `last_name`, `email`, `phone`, `comments`, and `status`.<br> - Learn how to define a Primary Key, use the AUTO_INCREMENT attribute, apply a UNIQUE constraint to the email field, and set the default value `active` for the status field.<br> - Practice using the INSERT INTO statement to add sample records to the `user` table according to the Workshop instructions.<br> - Use the `SELECT * FROM user;` statement to retrieve and verify all data stored in the table.<br> - Explore additional SQL commands for database management and inspection:<br>&nbsp;&nbsp;+ `USE database_name;`: Switch to the specified database.<br>&nbsp;&nbsp;+ `DESCRIBE table_name;`: Display the table structure, including column names, data types, and related attributes.<br>&nbsp;&nbsp;+ Query the `information_schema.tables` table to inspect database storage size based on total data and index sizes.<br> - Practice deploying the AWS User Management application using Node.js on EC2 by downloading its source code from GitHub with `git clone https://github.com/thienluhoan/000006-EC2.git`.<br> - Navigate to the project directory using `cd 000006-EC2` and inspect the source files required for application deployment.<br> - Create and configure the `.env` file using the `nano .env` text editor to define database connection environment variables, including DB_HOST, DB_NAME (`fcaj`), DB_USER (`admin`), and DB_PASS.<br> - Replace DB_HOST with the actual RDS DB Endpoint and use the credentials configured when creating the Database Instance.<br> - Learn about Bash Scripts and practice creating a `script.sh` file using `nano script.sh` to automate the preparation of the Node.js deployment environment on Amazon Linux 2023.<br> - Learn and practice using NVM (Node Version Manager) through a Bash Script to install Node.js LTS, select the default version, and verify the Node.js and NPM versions after installation.<br> - Practice installing PM2 globally through NPM to manage and monitor Node.js application processes.<br> - Practice initializing `package.json` using `npm init -y` when the file does not exist and installing the required libraries:<br>&nbsp;&nbsp;+ Express.<br>&nbsp;&nbsp;+ dotenv.<br>&nbsp;&nbsp;+ express-handlebars.<br>&nbsp;&nbsp;+ body-parser.<br>&nbsp;&nbsp;+ mysql.<br>&nbsp;&nbsp;+ Nodemon (Development Dependency).<br> - Learn how to configure NPM Scripts in `package.json` using the `npm pkg set` command, including `start` for running the application through PM2 and `dev` for using Nodemon during development.<br> - Practice configuring PM2 to start automatically with the Linux system through systemd to help manage application processes after the server restarts.<br> - Grant execution permission to the Bash Script using `chmod +x script.sh` and run `bash script.sh` to begin installing and configuring the environment.<br> - Use `source ~/.bashrc` to reload Terminal environment settings after installing Node.js through NVM.<br> - Start the application using `npm start`, use `pm2 save` to save the process list, and use `pm2 status` to check the application's operational status.<br> - Return to the EC2 Console, copy the Public IPv4 address of `ec2-instance`, and access the application through a browser using `http://<EC2-Public-IP>:5000`.<br> - Check the AWS User Management interface in the browser and verify that the application deployed on EC2 can operate and connect to the Amazon RDS database.<br> - Understand how EC2, RDS, VPC, and Security Groups work together to build a Web application system with separate application and database servers. | 19/11/2026 | 19/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Application Deployment](https://000005.awsfcaj.com/5-deploy-app/) |
| Friday | **Learn and Practice Amazon RDS Backup and Restore and Clean Up Resources After the Workshop**<br><br> - Learn about the Backup and Restore functionality of Amazon RDS, which helps protect data, recover databases, and maintain system continuity in the event of failures.<br> - Distinguish between Automated Backups and Manual DB Snapshots:<br>&nbsp;&nbsp;+ **Automated Backups:** Automatically managed backups provided by Amazon RDS that support database recovery to a specific point in time within the configured retention period.<br>&nbsp;&nbsp;+ **Manual DB Snapshots:** Backups manually created by users and retained until they are explicitly deleted.<br> - Learn about the Point-in-Time Recovery mechanism of Automated Backups and its ability to restore data to an appropriate point within the retention period.<br> - Access the AWS RDS Console, select Databases, and open the previously created DB Instance.<br> - Access the Maintenance & backups tab to inspect backup status, retention periods, the latest recovery point, and other information related to database maintenance.<br> - Learn how to view Database Snapshots in the Snapshots section and understand their role in protecting database data.<br> - Practice selecting a DB Snapshot for recovery and using the Restore function to create a new Database Instance from the selected Snapshot.<br> - Set the DB Instance Identifier of the restored database to `fcaj-2` according to the Workshop instructions.<br> - Review and configure the settings of the new Database Instance, including compute resources, storage, VPC, Subnet, and appropriate Security Groups.<br> - Keep the remaining settings according to the instructions and select Restore DB instance to start the database restoration process.<br> - Monitor the creation status of the `fcaj-2` DB Instance in the Amazon RDS interface and wait for the Restore process to complete.<br> - Verify that the new Database Instance appears in the Databases list and identify the separate DB Endpoint generated after restoration.<br> - Understand that restoring from a Snapshot creates an entirely new DB Instance with its own Endpoint; therefore, the application connection string must be updated when switching to the restored database.<br> - Learn how to verify connectivity and data integrity after restoration, and check Security Groups and related configurations to ensure appropriate access permissions.<br> - Review the completed Amazon RDS activities, including Database Instance creation, EC2 connectivity, Node.js application deployment, and database backup and restoration.<br> - Practice cleaning up the EC2 Instance by accessing EC2 Console → Instances, selecting `ec2-instance`, opening Instance state, and choosing Terminate (delete) instance according to the Workshop instructions.<br> - Access Amazon RDS, select the `db-instance` Database Instance, and use Modify to disable Enable deletion protection before deleting the database.<br> - Select Apply immediately to apply the change, then access Actions → Delete to remove the Database Instance.<br> - In the confirmation dialog, select I acknowledge that upon instance deletion, automated backups, including system snapshots and point-in-time recovery, will no longer be available; enter `delete me` and confirm Delete.<br> - Follow the same procedure to delete the `fcaj-2` Database Instance after checking whether any data needs to be retained.<br> - Understand that deleting an RDS Database Instance may remove its automated backups and associated recovery capabilities; create a Final Snapshot before deletion when data retention is required.<br> - Wait for the Database Instance deletion process to complete before deleting the `rds-subnet-group` DB Subnet Group from the Amazon RDS Subnet groups section.<br> - Access Amazon VPC, open Internet gateways, select the `rds-igw` Internet Gateway, and choose Actions → Detach from VPC to detach the Internet Gateway from the VPC.<br> - Access Your VPCs, select the `rds-vpc` VPC, and choose Actions → Delete VPC according to the Workshop instructions.<br> - Inspect related resources after cleanup, particularly EBS Snapshots and CloudWatch Logs that may still exist if they have not been deleted separately.<br> - Access the AWS Billing Dashboard to check for any remaining charges from Workshop resources and confirm that unnecessary test resources have been removed. | 20/11/2026 | 20/11/2026 | [Get Started with Amazon RDS](https://000005.awsfcaj.com/)<br>[Backup and Restore](https://000005.awsfcaj.com/6-backup/)<br>[Clean Up Resources](https://000005.awsfcaj.com/7-cleanup/) |

### Week 7 Achievements:

- Gained an overall understanding of Amazon Relational Database Service (Amazon RDS), including its role as a managed relational database service provided by AWS that supports database deployment, operation, backup, software updates, and resource scaling on AWS Cloud.

- Understood the role of Amazon RDS in applications that use relational databases, particularly systems that store structured data, use SQL, and support Online Transaction Processing (OLTP).

- Identified the database engines supported by Amazon RDS, including:
  - Amazon Aurora.
  - MySQL.
  - MariaDB.
  - Oracle.
  - Microsoft SQL Server.
  - PostgreSQL.

- Distinguished Amazon RDS from self-managed database deployments on EC2, particularly in terms of operating system management, software updates, backups, security, and resource scaling responsibilities.

- Understood the important Amazon RDS management features:
  - Automated Backups and Manual Snapshots.
  - Database Software Updates and Maintenance Windows.
  - Multi-AZ Deployment.
  - Read Replicas.
  - Database Endpoints.
  - Storage Scaling and Compute Scaling.
  - Encryption and Security Management.

- Understood the Amazon RDS storage options:
  - **General Purpose SSD (gp3/gp2):** Suitable for most general-purpose database workloads, providing balanced performance and cost efficiency.
  - **Provisioned IOPS SSD (io1/io2):** Suitable for database applications that require high and consistent read and write performance.
  - **Magnetic Storage:** A legacy storage option with limited performance that is not recommended for new deployments.

- Understood the High Availability and Disaster Recovery mechanisms of Amazon RDS:
  - **Multi-AZ Deployments:** Use a Standby Replica in a different Availability Zone, support synchronous data replication, and provide automatic failover when the primary DB Instance encounters a failure.
  - **Read Replicas:** Use asynchronous replication to support read workload scaling and certain disaster recovery scenarios.
  - **Global Databases:** Support data replication across AWS Regions to improve data accessibility and Disaster Recovery capabilities.

- Learned Amazon RDS security mechanisms, including data encryption at rest using AWS KMS, data encryption in transit using SSL/TLS, network isolation through VPC, and access control using IAM Policies.

- Understood the roles of DB Instances and DB Endpoints in Amazon RDS and learned how to locate database connection information through the AWS Management Console.

- Gained practical experience creating an Amazon VPC for RDS deployment, configuring the IPv4 CIDR Block `10.0.0.0/16`, selecting Default Tenancy, and establishing an appropriate network architecture.

- Practiced configuring the network environment with:
  - 2 Availability Zones.
  - 2 Public Subnets.
  - 2 Private Subnets.
  - No NAT Gateway or VPC Endpoint during the practical exercise to minimize additional costs.

- Understood how to enable automatic Public IPv4 assignment for Public Subnets and recognized the importance of not automatically assigning Public IPv4 addresses to Subnets intended for RDS database deployment.

- Gained practical experience creating and configuring two separate Security Groups:
  - **ec2-sg:** Controls connections to EC2 Instances through SSH (22), HTTP (80), HTTPS (443), and Custom TCP (5000).
  - **rds-sg:** Controls connections to RDS MySQL through port 3306, allowing access only from the `ec2-sg` Security Group.

- Understood the benefits of using separate Security Groups for EC2 and RDS to strengthen resource isolation and control connectivity between application servers and database servers.

- Learned how to create a DB Subnet Group named `rds-subnet-group`, select Subnets across at least two Availability Zones, and prioritize Private Subnets to improve database security.

- Gained practical experience launching an Amazon RDS Database Instance using the Full configuration method, selecting MySQL as the Database Engine, and configuring the required settings according to the Workshop instructions.

- Understood the important DB Instance configuration parameters:
  - DB Instance Identifier: `db-instance`.
  - Master Username: `admin`.
  - Credential Management: Self managed.
  - Instance Class: `db.m5.large`.
  - Storage Type: General Purpose SSD (gp3).
  - Allocated Storage: 20 GiB.
  - Initial Database Name: `fcaj`.
  - Public Access: No.
  - VPC Security Group: `rds-sg`.
  - DB Subnet Group: `rds-subnet-group`.
  - Deployment: Multi-AZ DB instance deployment (2 instances).

- Understood the benefits of Multi-AZ DB instance deployment in improving database availability, using synchronous replication, and supporting automatic failover when a failure occurs.

- Learned how to check DB Endpoints, Ports, and connection information in the Connectivity & security section of an RDS Database Instance.

- Understood how to monitor Amazon RDS activities through Log & events, including CloudWatch Alarms, Recent Events, and technical log files.

- Learned how to inspect Maintenance & backups to monitor maintenance schedules, pending updates, backup status, and Database Snapshots.

- Gained practical experience launching an EC2 Instance using Amazon Linux 2023, selecting the `t3.micro` Instance Type, creating the `kp-linux` Key Pair in `.pem` format, and configuring the VPC, Public Subnet, Public IPv4 address, and appropriate Security Group.

- Practiced connecting to an EC2 Instance through SSH using MobaXterm, the Public IPv4 address, username `ec2-user`, port 22, and the created private key.

- Understood the roles of Key Pairs, Public IP addresses, and Security Groups in establishing connections from a personal computer to an EC2 Instance; recognized the importance of protecting private keys and restricting SSH access.

- Learned how to prepare the Amazon Linux 2023 environment by updating system packages and installing Git and MariaDB Client using the following commands:
  - `sudo dnf update -y`
  - `sudo yum install git`
  - `sudo dnf install mariadb105`
  - `git --version && mariadb --version`

- Gained practical experience connecting from EC2 to Amazon RDS MySQL using the MySQL Command Line Client, the DB Endpoint, Port 3306, the configured Master Username, and Password.

- Understood the functions of basic SQL commands for database management:
  - `SHOW DATABASES;`: Displays the list of databases.
  - `CREATE DATABASE IF NOT EXISTS fcaj;`: Creates the database if it does not already exist.
  - `USE fcaj;`: Selects the database for subsequent operations.
  - `CREATE TABLE`: Creates a table and defines its structure.
  - `INSERT INTO`: Inserts records into a table.
  - `SELECT * FROM user;`: Retrieves all records from a table.

- Practiced creating the `user` table in the `fcaj` database with the following fields:
  - `id`: Primary Key using AUTO_INCREMENT.
  - `first_name`: First name.
  - `last_name`: Last name.
  - `email`: Email address with a UNIQUE constraint.
  - `phone`: Phone number.
  - `comments`: Additional comments.
  - `status`: User status using ENUM values `active` or `inactive`, with `active` as the default value.

- Gained practical experience inserting sample records into the `user` table and using SELECT statements to verify the data stored in Amazon RDS MySQL.

- Learned additional SQL commands for inspecting database structures and storage capacity, including `DESCRIBE table_name` and queries against `information_schema.tables`.

- Practiced downloading the AWS User Management application source code from GitHub using `git clone https://github.com/thienluhoan/000006-EC2.git` and preparing the project directory for deployment on Amazon EC2.

- Understood the role of the `.env` file in managing application configuration and database connection information for Amazon RDS, including DB_HOST, DB_NAME, DB_USER, and DB_PASS.

- Gained practical experience using NVM (Node Version Manager) to install Node.js LTS, configure the default version, and verify the Node.js and NPM versions after installation.

- Practiced using Bash Scripts to automate the preparation of the Node.js application deployment environment on Amazon Linux 2023.

- Learned how to install the application dependencies:
  - PM2 for managing Node.js processes.
  - Express for building Web applications.
  - dotenv for managing environment variables.
  - express-handlebars for using Handlebars templates.
  - body-parser for processing Request Body data.
  - mysql for connecting to MySQL databases.
  - Nodemon for supporting application development.

- Understood how to configure NPM Scripts in `package.json`, use PM2 to start applications, and use Nodemon to run applications in the Development environment.

- Practiced granting execution permissions to the Bash Script using `chmod +x script.sh`, running the script with `bash script.sh`, and reloading the Terminal environment using `source ~/.bashrc`.

- Gained practical experience starting and managing Node.js applications through the following commands:
  - `npm start`: Starts the application through PM2.
  - `pm2 save`: Saves the process list to support process restoration after the server restarts.
  - `pm2 status`: Checks the status, CPU usage, memory usage, and restart count of application processes.

- Understood how to configure PM2 to start automatically with the Linux system through systemd to help maintain application availability after an EC2 Instance restart.

- Practiced accessing the AWS User Management application through the EC2 Public IPv4 address combined with port 5000 and verifying the application interface in a web browser.

- Understood the AWS application deployment architecture, in which:
  - Amazon EC2 acts as the application server.
  - Amazon RDS acts as the database server.
  - Amazon VPC provides an isolated network environment for resources.
  - Security Groups control access between EC2 and RDS.
  - The DB Endpoint supports connectivity between the application and the database.

- Understood the roles of Automated Backups and Manual DB Snapshots in protecting data, supporting database recovery, and maintaining system continuity.

- Distinguished between the two backup methods:
  - **Automated Backups:** Automatically managed by Amazon RDS and support Point-in-Time Recovery within the configured retention period.
  - **Manual DB Snapshots:** Manually created by users and retained until explicitly deleted.

- Practiced checking backup status in Maintenance & backups, managing Database Snapshots, and restoring a Snapshot to create a new DB Instance named `fcaj-2`.

- Understood that restoring from a Snapshot creates a new Database Instance with a separate Endpoint, and recognized the need to update the application's connection string when switching to the restored database.

- Learned how to verify data integrity, connectivity, and Security Group configurations after restoring a Database Instance.

- Understood the resource cleanup procedures after the Workshop, including:
  - Terminating the `ec2-instance` EC2 Instance.
  - Disabling Deletion Protection before deleting RDS Database Instances.
  - Confirming the deletion of `db-instance` and `fcaj-2`.
  - Deleting the `rds-subnet-group` DB Subnet Group after the Database Instance deletion process has completed.
  - Detaching the `rds-igw` Internet Gateway from the VPC.
  - Deleting the `rds-vpc` VPC.
  - Checking for remaining EBS Snapshots and CloudWatch Logs that may need to be deleted separately.

- Recognized the importance of creating a Final Snapshot before deleting a database when data retention is required; understood that deleting a Database Instance may result in the loss of associated Automated Backups and Point-in-Time Recovery capabilities.

- Understood the importance of checking the AWS Billing Dashboard after completing the Workshop to identify remaining resources and minimize unexpected costs.

- Consolidated practical knowledge and experience with Amazon RDS in building network environments, deploying MySQL databases, connecting applications from EC2, deploying Node.js applications, and backing up and restoring data on AWS Cloud.