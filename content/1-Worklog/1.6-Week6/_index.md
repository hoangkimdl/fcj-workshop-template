---
title: "Week 6 Worklog"
date: 2026-11-02
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

- Learn about Amazon Simple Storage Service (Amazon S3), its role as an object storage service in AWS Cloud, and important concepts such as Buckets, Objects, Storage Classes, and Access Control.
- Understand how to create and configure Amazon S3 Buckets, manage stored objects, and practice uploading data from a personal computer to S3.
- Practice deploying Static Website Hosting directly on Amazon S3, configuring public access permissions for website files, and verifying website accessibility through the Website Endpoint.
- Learn about Amazon CloudFront and practice integrating CloudFront with S3 to distribute website content, improve access speed, and enhance the security of stored data.
- Learn and practice Amazon S3 Bucket Versioning to retain multiple versions of objects, track changes, and restore data when necessary.
- Practice moving objects between S3 Buckets using the Move Objects feature and learn about Amazon S3 Cross-Region Replication (CRR) to automatically replicate data across different AWS Regions.
- Learn security, performance optimization, and cost management best practices when using Amazon S3, including Block Public Access, Bucket Policies, Encryption, Lifecycle Policies, and CloudFront Origin Access Control (OAC).
- Understand the procedures for checking, cleaning up, and deleting Amazon S3 and CloudFront resources after completing the Workshop to minimize unnecessary costs.

### Tasks to Be Completed During the Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | **Learn About Amazon S3 and Practice Creating a Bucket and Uploading Data to S3**<br><br> - Learn about Amazon Simple Storage Service (Amazon S3), a scalable object storage service that provides high availability, durability, security, and performance on AWS Cloud.<br> - Learn about the role of Amazon S3 in common use cases such as data storage, static website hosting, data backup and recovery, application storage, data analytics, and Disaster Recovery.<br> - Distinguish between the two basic components of Amazon S3:<br>&nbsp;&nbsp;+ **S3 Bucket:** A top-level container used to store and organize data objects. Each Bucket has a globally unique name and is created in a specific AWS Region.<br>&nbsp;&nbsp;+ **S3 Object:** The actual data object stored inside a Bucket, including its data content and related Metadata.<br> - Learn about Object characteristics such as Object Keys, Metadata, storage capacity, and object-level access permissions.<br> - Learn about Amazon S3 Storage Classes, including S3 Standard, S3 Intelligent-Tiering, S3 Standard-IA, S3 Glacier, and S3 Glacier Deep Archive; distinguish the purposes of each storage class based on data access frequency and storage requirements.<br> - Learn about important Amazon S3 features such as Encryption, Access Control, Versioning, Lifecycle Management, Cross-Region Replication, and S3 Storage Lens.<br> - Access the AWS Management Console and open Amazon S3 through the service search bar.<br> - Practice creating a new S3 Bucket using the Create bucket function and select AWS Region `ap-southeast-1` (Singapore) according to the Workshop instructions.<br> - Name the Bucket using the pattern `aws-first-cloud-ai-journey-1902`; if the name is already in use, add or change the numbers to ensure global uniqueness.<br> - Configure Object Ownership with the ACLs disabled (recommended) option, keep Block all public access enabled, disable Bucket Versioning during the initial setup, and check the default SSE-S3 encryption setting.<br> - Keep the advanced settings at their default values, review the configuration, and complete the S3 Bucket creation process.<br> - Check the Bucket information after creation, including its name, AWS Region, access permissions, and initial storage status.<br> - Practice downloading sample website source code from GitHub to a personal computer and extracting the `S3-Website-main` directory to prepare the website deployment data.<br> - Access the newly created S3 Bucket, select Upload, and upload the entire extracted website directory and its files.<br> - Check the list of Objects in the Bucket after uploading to verify that the HTML, CSS, JavaScript, image files, and other related website resources have been stored successfully.<br> - Learn how to organize data in S3 using Object Keys and Prefixes to make file management more convenient. | 02/11/2026 | 02/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Introduction](https://000057.awsfcaj.com/1-introduce/)<br>[Create S3 Bucket](https://000057.awsfcaj.com/2-prerequiste/2.1-creates3bucket/)<br>[Download Data](https://000057.awsfcaj.com/2-prerequiste/2.2-uploaddata/) |
| Tuesday | **Practice Deploying Static Website Hosting on Amazon S3 and Configuring Public Access Permissions**<br><br> - Learn about Static Website Hosting on Amazon S3, which allows static content such as HTML, CSS, JavaScript, and images to be stored and distributed directly without deploying a separate web server.<br> - Learn about the benefits of Static Website Hosting, including cost savings, automatic scalability, high reliability, and reduced server management requirements.<br> - Practice accessing the S3 Bucket, opening the Properties tab, and locating the Static website hosting section.<br> - Enable Static Website Hosting by selecting Enable, choosing the Host a static website option, and configuring `index.html` as the default document and `error.html` as the optional error document.<br> - Save the configuration and check the Website Endpoint generated by Amazon S3 after enabling static website hosting.<br> - Learn the differences between the Website Endpoint and the S3 Bucket Endpoint, and understand that the Website Endpoint uses HTTP and requires CloudFront to distribute the website over HTTPS.<br> - Learn about Amazon S3 Block Public Access and its role in preventing unintended public access to Buckets and Objects.<br> - Practice accessing the Permissions tab, opening Block public access, and unchecking Block all public access as required for the Static Website Hosting exercise.<br> - Confirm the change by entering `confirm` in the confirmation dialog and saving the public access configuration.<br> - Learn about S3 access control levels, including Bucket-level permissions and Object-level permissions; distinguish the roles of ACLs, Bucket Policies, and IAM Policies.<br> - Practice changing Object Ownership from Bucket owner enforced to Bucket owner preferred and enabling ACLs to support object-level access configuration.<br> - In the Object Ownership section, select ACLs enabled, confirm I acknowledge that ACLs will be restored, and save the configuration according to the Workshop instructions.<br> - Access the Objects tab, select website files that need to be publicly accessible, including HTML, CSS, JavaScript, and images, then select Actions → Make public using ACL to grant public read access to the selected Objects.<br> - Check the access permissions of the Objects after configuration and verify that the website files can be downloaded by Internet users.<br> - Access Properties → Static website hosting, copy the Bucket Website Endpoint, and open it in a browser to verify the sample website interface.<br> - Use the browser Developer Tools, open the Network tab, and reload the page to observe the website loading time through the S3 Website Endpoint before integrating CloudFront.<br> - Recognize the security risks associated with allowing public access to objects and understand that only content that genuinely needs to be publicly accessible should receive the appropriate permissions. | 03/11/2026 | 03/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Enable Static Website Feature](https://000057.awsfcaj.com/3-staticwebsite/)<br>[Configuring Public Access Block](https://000057.awsfcaj.com/4-blockpublicaccess/)<br>[Configuring Public Objects](https://000057.awsfcaj.com/5-publicobject/)<br>[Test Website](https://000057.awsfcaj.com/6-testwebsite/) |
| Wednesday | **Learn and Practice Integrating Amazon CloudFront with S3 to Distribute Website Content**<br><br> - Learn about Amazon CloudFront and its role as a Content Delivery Network (CDN) for distributing content through a global network of Edge Locations.<br> - Understand how CloudFront works by distributing content from edge locations close to users to reduce latency, improve page loading speed, and enhance website accessibility.<br> - Learn the benefits of integrating Amazon CloudFront with S3, particularly the ability to distribute website content without directly exposing the S3 Bucket to the public.<br> - Return to the S3 Bucket, access Permissions, and re-enable Block all public access to prevent direct public access to the Bucket and Objects from the Internet.<br> - Confirm the change by entering `confirm`, save the configuration, and verify that Block Public Access has been enabled.<br> - Practice opening an incognito browser window using `Ctrl + Shift + N` and accessing the S3 Website Endpoint again to check its accessibility after enabling Block Public Access.<br> - Learn the differences between accessing a website directly through the S3 Endpoint and accessing it through the CloudFront Distribution Domain Name.<br> - Access Amazon CloudFront and select Create distribution to create a new Distribution.<br> - Select the free plan recommended by the Workshop for learning purposes and provide an appropriate Distribution Name.<br> - In the Origin section, select Amazon S3 as the Origin Type and use Browse S3 to select the previously created Bucket as the content source.<br> - Keep the default settings according to the Workshop instructions, review the configuration, and select Create distribution to complete the creation process.<br> - Monitor the Distribution deployment status in the CloudFront interface and learn about the Deploying status while AWS distributes the configuration across Edge Locations.<br> - Practice editing the Distribution and configuring the Default root object as `index.html` so that CloudFront automatically displays the homepage when users access the Distribution Domain Name.<br> - Access the Origins section, select the newly created Origin, open its configuration settings, and copy the Bucket Policy provided by CloudFront.<br> - Return to the S3 Bucket, access Permissions → Bucket policy, paste the copied Bucket Policy, and save the configuration to grant CloudFront the appropriate access permissions.<br> - Wait for CloudFront to complete deployment, check the Distribution status, and copy the Distribution Domain Name.<br> - Practice opening the Distribution Domain Name in a browser to verify that the website is distributed through CloudFront without requiring the S3 Bucket to be publicly accessible.<br> - Use Developer Tools → Network to check the website loading time through CloudFront and compare it with the results obtained when accessing the S3 Website Endpoint directly.<br> - Learn how to inspect Response Headers and the `x-amz-cf-pop` attribute to identify the Point of Presence (PoP) serving the website content; recognize the `SGN50-P2` example corresponding to Ho Chi Minh City in the Workshop instructions.<br> - Compare page loading results before and after integrating CloudFront to understand the role of Edge Locations and content distribution mechanisms in reducing latency.<br> - Further explore Origin Access Control (OAC) and the use of Bucket Policies to grant CloudFront access instead of exposing the entire Bucket publicly in real-world deployments. | 04/11/2026 | 04/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Accelerate Static Websites with CloudFront](https://000057.awsfcaj.com/7-cloudfront/)<br>[Block All Public Access](https://000057.awsfcaj.com/7-cloudfront/7.1-block_all_public_access/)<br>[Configure Amazon CloudFront](https://000057.awsfcaj.com/7-cloudfront/7.2-configure_amazon_cloudfront/)<br>[Test Amazon CloudFront](https://000057.awsfcaj.com/7-cloudfront/7.3-test_cloudfront/) |
| Thursday | **Learn and Practice Amazon S3 Bucket Versioning and Move Objects Between Buckets**<br><br> - Learn about Amazon S3 Bucket Versioning, a feature that allows multiple versions of the same object to be retained in a Bucket to prevent data loss caused by accidental overwrites or deletions.<br> - Learn about the benefits of Versioning, including data protection, change history tracking, previous version recovery, data retention requirements, and collaboration support.<br> - Understand how Versioning works, in which each Object version is assigned a unique Version ID; uploading a new version does not permanently overwrite the previous version.<br> - Distinguish between the three Bucket Versioning states: Unversioned, Versioning-enabled, and Versioning-suspended; understand how new versions are created and how previous versions are retained in each state.<br> - Practice accessing the S3 Bucket, opening Properties → Bucket Versioning, and selecting Edit to enable Versioning.<br> - Open the `index.html` file in the source code directory downloaded to the personal computer, use Notepad to edit the content inside the body tag according to the Workshop instructions, and change the text from `AWS First Cloud AI Journey` to `HỌC CLOUD AI VUI BIẾT BAO <3`.<br> - Save the changes using `Ctrl + S` and upload the modified `index.html` file to the S3 Bucket using the Upload function.<br> - Search for `index.html`, enable the Show versions option to inspect the versions of the same Object, and verify that S3 has retained two versions with different modification timestamps.<br> - Learn how Versioning affects storage capacity and AWS costs, recognizing that each stored version occupies storage space and may generate additional charges.<br> - Learn about the role of Lifecycle Policies in automatically managing previous versions and explore the use of MFA Delete to strengthen data protection.<br> - Learn about the Move Objects feature in Amazon S3, which allows objects to be moved to a different folder (Prefix) within the same Bucket or to another Bucket.<br> - Practice creating a new S3 Bucket using the pattern `aws-first-cloud-ai-journey-xxxx-move`, keeping the default settings according to the Workshop instructions, and completing the destination Bucket creation process.<br> - Access the source Bucket, select all Objects, and use Actions → Calculate total size to check the total number and storage size of the data before moving it.<br> - Practice selecting Actions → Move, choosing General purpose bucket as the destination type, opening Browse S3, and selecting the newly created destination Bucket.<br> - Keep the Copy source settings options in the Additional copy settings section unchanged, then perform the Move operation to start transferring the data.<br> - Monitor the moving process, close the notification after completion, and access the destination Bucket to check its list of Objects.<br> - Use Calculate total size in the destination Bucket to compare the number of Objects and total storage size after the move, confirming that the objects have been transferred successfully.<br> - Understand the benefits of moving Objects when organizing, classifying, and managing data across different S3 Buckets. | 05/11/2026 | 05/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Bucket Versioning](https://000057.awsfcaj.com/8-versioning/)<br>[Move Objects](https://000057.awsfcaj.com/9-moveobject/) |
| Friday | **Practice Amazon S3 Cross-Region Replication and Review and Clean Up Resources After the Workshop**<br><br> - Learn about Amazon S3 Cross-Region Replication (CRR), a feature that automatically replicates Objects between S3 Buckets located in different AWS Regions.<br> - Learn about the benefits of CRR in improving data redundancy, supporting Disaster Recovery, meeting compliance requirements, distributing data geographically, and maintaining system continuity.<br> - Understand the asynchronous data replication mechanism, in which Objects are automatically replicated to the destination Bucket; the Workshop indicates that replication may generally complete within approximately 15 minutes, depending on actual conditions.<br> - Learn about the prerequisites for configuring CRR, including enabling Bucket Versioning on both the Source Bucket and Destination Bucket, creating a Replication Rule, and using an IAM Role to grant replication permissions.<br> - Learn about the factors to consider when selecting a destination AWS Region for replication, including compliance requirements, latency, storage costs, data transfer costs, service availability, and disaster recovery capabilities.<br> - Practice creating a new Destination Bucket using the pattern `aws-first-cloud-ai-journey-xxxx-cross` in the N. Virginia Region (`us-east-1`), while the Source Bucket is located in Singapore (`ap-southeast-1`).<br> - Select the previously created Source Bucket and upload the website data to it again according to the Workshop instructions because the Objects were moved to another Bucket in the previous Move Objects exercise.<br> - Access Management → Replication rules in the Source Bucket and select Create replication rule to configure a new data replication rule.<br> - Name the Replication Rule `PrimaryToSecondary`, set its status to Enabled, and select Apply to all objects in the bucket to apply the rule to all Objects within the Bucket's scope.<br> - In the Destination section, select Choose a bucket in this account to replicate data to another Bucket within the same AWS Account.<br> - Use Browse S3 to select the Destination Bucket with the `-cross` suffix in the N. Virginia Region (`us-east-1`).<br> - Enable Bucket Versioning for the Destination Bucket as required by CRR.<br> - In the IAM Role section, select Create new role so that AWS can create an IAM Role and grant the required permissions for the replication process.<br> - Keep the remaining settings at their default values, save the Replication Rule, and select No, do not replicate existing objects to prevent previously existing Objects from being replicated.<br> - Access the Destination Bucket in the N. Virginia Region and check its initial list of Objects before uploading new data to the Source Bucket.<br> - Practice uploading a new image file from the `images` directory to the Source Bucket using the Upload function to test the Replication Rule.<br> - Revisit the Destination Bucket, refresh the page, and verify the appearance of the newly uploaded image after the replication process is completed.<br> - Learn and summarize Amazon S3 security best practices in the Notes & Best Practices section, including:<br>&nbsp;&nbsp;+ Keep Block Public Access enabled in Production environments.<br>&nbsp;&nbsp;+ Prioritize using CloudFront with Origin Access Control (OAC) instead of exposing S3 Buckets directly to the public.<br>&nbsp;&nbsp;+ Use Bucket Policies to control access permissions in detail.<br>&nbsp;&nbsp;+ Enable default encryption using SSE-S3 or SSE-KMS, selecting the appropriate encryption method based on data sensitivity.<br> - Learn performance optimization practices, including configuring CloudFront Cache Behaviors, TTL, Compression, HTTP/2, IPv6, S3 Transfer Acceleration, and Multipart Upload for files larger than 100 MB.<br> - Learn cost optimization methods, including using S3 Intelligent-Tiering, Lifecycle Policies, S3 Storage Lens, managing previous object versions, and monitoring data transfer costs.<br> - Learn common errors when using Amazon S3 and CloudFront, particularly 403 Forbidden errors caused by incorrect Block Public Access settings, Bucket Policies, or CloudFront access permissions.<br> - Distinguish between S3 Website Endpoint and S3 Bucket Endpoint, understanding their differences in Static Website Hosting, HTTPS, OAC, and OAI support.<br> - Learn about Cross-Origin Resource Sharing (CORS), understand why browsers block requests between different origins, and explore how to configure CORS according to access requirements.<br> - Practice cleaning up resources after the Workshop by accessing Amazon S3, selecting the relevant Buckets, using Empty to delete all Objects, and then selecting Delete bucket.<br> - Practice cleaning up CloudFront Distributions by accessing Amazon CloudFront, selecting the created Distribution, choosing Disable, and waiting for the disabling process to complete before selecting Delete.<br> - Review the S3 Bucket and CloudFront Distribution lists after cleanup to ensure that unused test resources have been removed and unnecessary costs are minimized. | 06/11/2026 | 06/11/2026 | [Start With Amazon S3](https://000057.awsfcaj.com/)<br>[Replication Object Multi Region](https://000057.awsfcaj.com/10-s3ccr/)<br>[Clean Up Resources](https://000057.awsfcaj.com/11-cleanup/)<br>[Notes & Best Practices](https://000057.awsfcaj.com/12-notes/) |

### Week 6 Achievements:

- Gained an overall understanding of Amazon Simple Storage Service (Amazon S3), including its role as an object storage service in AWS Cloud and its benefits in terms of scalability, availability, durability, security, and cost efficiency.

- Understood the storage structure of Amazon S3 and distinguished between its two fundamental components:
  - **S3 Bucket:** A top-level container used to store and organize data objects. Each Bucket has a globally unique name and belongs to a specific AWS Region.
  - **S3 Object:** The actual data object stored inside a Bucket, including its content, Object Key, and related Metadata.

- Learned about Amazon S3 Storage Classes and their respective purposes:
  - **S3 Standard:** Suitable for frequently accessed data.
  - **S3 Intelligent-Tiering:** Automatically optimizes storage classes based on data access patterns.
  - **S3 Standard-IA:** Suitable for infrequently accessed data that still requires quick retrieval.
  - **S3 Glacier:** Suitable for long-term data storage, with retrieval times depending on the selected retrieval configuration.
  - **S3 Glacier Deep Archive:** Suitable for long-term data retention with very infrequent access requirements.

- Understood important Amazon S3 features such as Encryption, Access Control, Versioning, Lifecycle Management, Cross-Region Replication, and S3 Storage Lens.

- Gained practical experience in creating and configuring Amazon S3 Buckets through the AWS Management Console, selecting AWS Regions, setting globally unique Bucket names, and configuring default security settings.

- Understood the important settings involved in creating an S3 Bucket:
  - Object Ownership using the ACLs disabled (recommended) option.
  - Block all public access enabled by default.
  - Bucket Versioning disabled during initial creation.
  - Default Encryption using SSE-S3.
  - Selecting an appropriate AWS Region based on data storage requirements.

- Practiced downloading sample website source code from GitHub and uploading it to Amazon S3, learning how to use the Upload function to store HTML, CSS, JavaScript, image files, and other website resources as Objects in a Bucket.

- Understood the operating principles of Static Website Hosting on Amazon S3 and practiced deploying a static website through the following steps:
  - Enabling Static Website Hosting in the Properties section.
  - Selecting the Host a static website option.
  - Setting `index.html` as the default document.
  - Configuring `error.html` as an optional error document.
  - Checking the Website Endpoint after enabling the feature.

- Understood the differences between the Website Endpoint and S3 Bucket Endpoint, particularly the use of HTTP for static website delivery and the need for CloudFront when HTTPS support is required.

- Understood Amazon S3 access control mechanisms, distinguished between Bucket-level and Object-level permissions, and recognized the roles of ACLs, Bucket Policies, and IAM Policies.

- Gained practical experience in configuring public access permissions for website objects by:
  - Modifying Block all public access according to the practical exercise requirements.
  - Enabling ACLs in Object Ownership.
  - Switching to the Bucket owner preferred option.
  - Using Make public using ACL to grant public read access to selected Objects.
  - Checking website file access permissions after configuration.

- Practiced verifying Static Website functionality through the Website Endpoint in a browser, confirming that the website interface was displayed correctly and using Developer Tools to observe page loading time before integrating CloudFront.

- Understood the role of Amazon CloudFront in content distribution through a Content Delivery Network (CDN), using Edge Locations to reduce latency and improve users' website access speeds.

- Practiced creating a CloudFront Distribution and integrating it with an S3 Bucket as the Origin, including:
  - Creating a new Distribution in Amazon CloudFront.
  - Selecting an appropriate plan for the practical exercise.
  - Choosing Amazon S3 as the Origin Type.
  - Selecting an S3 Bucket as the content source.
  - Configuring the Default root object as `index.html`.
  - Updating the Bucket Policy provided by CloudFront in the S3 Bucket.
  - Monitoring the Distribution deployment status.

- Understood how Amazon S3 and CloudFront can work together to distribute website content without directly exposing the S3 Bucket to the public; practiced re-enabling Block all public access after completing the direct public website access test through S3.

- Gained practical experience in testing websites through the CloudFront Distribution Domain Name, checking page loading time through Developer Tools → Network, and comparing the results with direct access through the S3 Website Endpoint.

- Understood how to inspect Response Headers and the `x-amz-cf-pop` attribute to identify the Point of Presence (PoP) serving website content; recognized the `SGN50-P2` example corresponding to Ho Chi Minh City in the Workshop.

- Recognized the benefits of CloudFront in distributing content from Edge Locations close to users, reducing latency, improving page loading speed, and enhancing the website access experience.

- Understood the purpose of Amazon S3 Bucket Versioning and its ability to retain multiple versions of the same Object, helping restore data after accidental overwrites or deletions.

- Distinguished between the three Versioning states:
  - **Unversioned:** The default state in which version management has not been enabled.
  - **Versioning-enabled:** Allows a new version to be created whenever an Object is uploaded or modified.
  - **Versioning-suspended:** Suspends the creation of new versions while retaining previously stored versions.

- Understood the Version ID and Delete Marker mechanisms in object version management and recognized the benefits of Versioning for data protection and change history tracking.

- Gained practical experience in enabling Versioning, modifying the contents of the `index.html` file, uploading a new version to S3, and using Show versions to inspect two versions of the same Object.

- Recognized the impact of Versioning on storage capacity and AWS costs, understood that each object version is billed separately for storage, and learned the importance of using Lifecycle Policies to manage previous versions that are no longer needed.

- Practiced moving Objects between S3 Buckets using Actions → Move, learning how to select source and destination Buckets, calculate total data size, and verify the results after completing the operation.

- Understood the benefits of moving Objects when organizing, classifying, and managing data across different S3 Buckets, as well as how to compare the number and total size of objects before and after moving them.

- Gained an overall understanding of Amazon S3 Cross-Region Replication (CRR), including its ability to automatically replicate Objects between Buckets located in different AWS Regions to improve data redundancy and recovery capabilities.

- Understood the main benefits of Cross-Region Replication:
  - **Disaster Recovery:** Helps protect data in the event of an incident in an AWS Region.
  - **Compliance:** Supports geographic data distribution and storage requirements.
  - **Latency Reduction:** Helps distribute data from locations suitable for users.
  - **Data Sovereignty:** Supports maintaining data replicas in specific geographic locations.
  - **Operational Excellence:** Contributes to maintaining system continuity.

- Learned the prerequisites for configuring CRR:
  - Enable Versioning on both the Source Bucket and Destination Bucket.
  - Create and enable a Replication Rule.
  - Select the scope of Objects to be replicated.
  - Use an IAM Role to grant replication permissions.
  - Select an appropriate AWS Region and Destination Bucket.

- Gained practical experience configuring Cross-Region Replication from Singapore (`ap-southeast-1`) to N. Virginia (`us-east-1`), creating the `PrimaryToSecondary` Replication Rule, and selecting Apply to all objects in the bucket.

- Understood how IAM Roles grant Amazon S3 the permissions required to replicate data between Buckets, and recognized the No, do not replicate existing objects option used in the practical exercise.

- Practiced uploading a new image file to the Source Bucket, accessing the Destination Bucket, and verifying the result after the replication process was completed.

- Recognized the importance of CRR for Disaster Recovery, Geographic Redundancy, Data Availability, and data protection in the event of an incident affecting an AWS Region.

- Learned Amazon S3 security best practices for real-world environments, including:
  - Keeping Block Public Access enabled in Production environments.
  - Prioritizing CloudFront with Origin Access Control (OAC) instead of directly exposing S3 Buckets to the public.
  - Using Bucket Policies to control access permissions in detail.
  - Enabling default encryption with SSE-S3 or SSE-KMS.
  - Selecting an encryption method appropriate for the sensitivity of the stored data.

- Learned Amazon S3 and CloudFront performance optimization practices, including configuring Cache Behaviors, TTL, Compression, HTTP/2, IPv6, S3 Transfer Acceleration, and Multipart Upload for files larger than 100 MB.

- Learned several AWS cost optimization methods:
  - Using S3 Intelligent-Tiering when data access frequency is uncertain.
  - Configuring Lifecycle Policies to automatically transition Storage Classes.
  - Using S3 Storage Lens to monitor storage usage and costs.
  - Managing and deleting unnecessary previous Object versions.
  - Monitoring data transfer costs and using CloudFront appropriately.

- Learned common errors when deploying Amazon S3 and CloudFront, particularly 403 Forbidden errors caused by incorrect Block Public Access settings, Bucket Policies, or CloudFront access permissions.

- Distinguished between S3 Website Endpoint and S3 Bucket Endpoint, understood their differences in Static Website Hosting, OAC, and OAI support, and recognized that the S3 Bucket Endpoint is more suitable when integrating CloudFront with OAC in security-focused environments.

- Understood Cross-Origin Resource Sharing (CORS), the reasons browsers may block requests between different origins, and the role of CORS configuration in controlling resource access.

- Learned the resource cleanup process after completing the Workshop, including:
  - Emptying related S3 Buckets using the Empty function.
  - Deleting test S3 Buckets after removing their contents.
  - Disabling CloudFront Distributions and waiting for the disabling process to complete.
  - Deleting CloudFront Distributions when they are no longer needed.

- Recognized the importance of managing AWS resources, data, and costs, particularly for Amazon S3 and CloudFront; understood the need to check remaining Buckets, Objects, data versions, and Distributions after completing practical exercises.

- Consolidated practical knowledge and experience with Amazon S3 in object storage, static website hosting, content distribution through CloudFront, version management, data movement, and cross-region data replication on AWS Cloud.