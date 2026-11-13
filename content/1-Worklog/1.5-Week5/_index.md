---
title: "Week 5 Worklog"
date: 2026-11-02
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

- Learn about AWS CloudShell, its role, and the benefits of using an AWS-managed command-line environment directly through a web browser.
- Understand how to access AWS CloudShell through the AWS Management Console, initialize a CloudShell Environment, and become familiar with the Terminal interface.
- Learn basic Linux commands commonly used in AWS CloudShell to manage directories, files, and access permissions.
- Practice using commands such as `pwd`, `ls -la`, `mkdir`, `cd`, `touch`, `vi`, and `cat` to perform file and directory operations in the CloudShell environment.
- Learn about AWS Command Line Interface (AWS CLI), its functions, and its capabilities for managing AWS services through command-line operations.
- Practice using AWS CLI to check the tool version, list Amazon S3 Buckets, and retrieve EC2 Instance information in an AWS account.
- Learn how to upload files from a personal computer to CloudShell and download files from CloudShell to a personal computer through the file management interface.
- Understand how to manage and delete a CloudShell Environment after completing the practical exercises to avoid unnecessary data storage.

### Tasks to Be Completed During the Week:

| Day | Tasks | Start Date | Completion Date | Reference Materials |
|---|---|---|---|---|
| Monday | **Learn About AWS CloudShell and Initialize a CloudShell Environment**<br><br> - Learn about AWS CloudShell, a fully managed command-line environment provided by AWS that can be accessed directly through a web browser.<br> - Understand the role of CloudShell in performing AWS resource management operations without requiring command-line environment installation or configuration on a personal computer.<br> - Learn about the tools integrated into CloudShell, including AWS CLI, AWS SDKs, and other essential command-line tools.<br> - Learn about the CloudShell authentication mechanism, which inherits access permissions from the IAM User or IAM Role currently used in the AWS Management Console.<br> - Learn about the storage capacity allocated to the `$HOME` directory, which provides 1 GB of persistent storage for the CloudShell environment.<br> - Practice signing in to the AWS Management Console using an existing AWS account.<br> - Use the service search bar in the AWS Management Console, enter the keyword CloudShell, and select the AWS CloudShell service.<br> - Practice opening a CloudShell Environment through the Terminal interface and selecting the `us-west-1` environment as instructed in the Workshop.<br> - Become familiar with the Terminal interface, command input area, and interaction methods in the CloudShell environment.<br> - Verify CloudShell accessibility and prepare the environment for subsequent practical exercises. | 02/11/2026 | 02/11/2026 | [Getting Started with AWS CloudShell](https://000049.awsfcaj.com/) |
| Tuesday | **Learn and Practice Basic Linux Commands in AWS CloudShell**<br><br> - Learn about the role of basic Linux commands in managing directories, files, and system information through the command-line interface.<br> - Practice using the `pwd` command to display the path of the current working directory in CloudShell.<br> - Practice using the `ls -la` command to list files and directories, including hidden items and information about user and group permissions.<br> - Learn the meaning of the `rwx` permission types, including Read, Write, and Execute.<br> - Distinguish between the three permission categories: User, Group, and Other in the Linux operating system.<br> - Practice using the `mkdir project` command to create a new directory named `project`.<br> - Use the `cd project` command to navigate into the newly created directory.<br> - Use the `touch test.txt` command to create a file named `test.txt` inside the `project` directory.<br> - Practice using the `vi test.txt` command to open and edit the file.<br> - Learn how to press `i` to enter Insert mode, enter the sample content `Hello First Cloud AI Journey!`, then press `Esc` and use the `:wq` command to save the changes and exit the editor.<br> - Use the `cat test.txt` command to display and verify the content saved in the file.<br> - Check the directory structure and files created during the practical exercises. | 03/11/2026 | 03/11/2026 | [Getting Started with AWS CloudShell - Basic Commands](https://000049.awsfcaj.com/2-basicfeature/) |
| Wednesday | **Learn and Practice Using AWS Command Line Interface (AWS CLI)**<br><br> - Learn about AWS Command Line Interface (AWS CLI), a tool that allows users to manage and interact with various AWS services through commands in the Terminal.<br> - Understand how AWS CLI can be used to manage AWS resources, retrieve service information, and automate operations through scripts containing multiple commands.<br> - Learn that AWS CLI is already installed and preconfigured in the AWS CloudShell environment, so manual installation is not required.<br> - Practice using the `aws --version` command to check the AWS CLI version currently available in CloudShell.<br> - Use the `aws s3 ls` command to list Amazon S3 Buckets belonging to the currently accessed AWS account.<br> - Use the `aws ec2 describe-instances` command to retrieve and display information about EC2 Instances in the AWS account.<br> - Learn how AWS CLI interacts with AWS services based on the permissions of the current IAM User or IAM Role.<br> - Practice reading the output returned by AWS CLI commands and identifying basic information about AWS resources.<br> - Understand the benefits of AWS CLI in reducing operations performed through the AWS Management Console, supporting resource inspection, and carrying out administrative tasks more efficiently. | 04/11/2026 | 04/11/2026 | [Getting Started with AWS CloudShell - Using AWS CLI](https://000049.awsfcaj.com/3-useawscli/) |
| Thursday | **Practice Uploading and Downloading Files in AWS CloudShell**<br><br> - Learn about the file management features of AWS CloudShell and its ability to transfer data between a personal computer and the CloudShell environment.<br> - Practice creating a file named `test.txt` on a personal computer and entering sample content to prepare for the upload operation.<br> - Access the AWS CloudShell interface, select Actions → Upload file, and choose the `test.txt` file from the personal computer.<br> - Check the confirmation message indicating that the file has been uploaded successfully after completing the Upload file operation.<br> - Use the `ls` command in CloudShell to verify that the uploaded file is present.<br> - Use the `cat test.txt` command to read and verify the content of the uploaded file.<br> - Practice creating a new file named `test1.txt` using the `touch test1.txt` command to prepare for the download operation.<br> - Use the `vi test1.txt` command to open and edit the file, enter the sample content `Hello FCAJ!`, then press `Esc` and use `:wq` to save the changes and exit.<br> - Use the `ls` command to verify the name of the newly created file in the CloudShell environment.<br> - Practice selecting Actions → Download file, entering the filename `test1.txt`, and clicking Download to transfer the file from CloudShell to the personal computer.<br> - Open the downloaded file on the personal computer and verify its content to confirm that the download operation was successful.<br> - Understand the file transfer process between a personal computer and AWS CloudShell to support AWS resource management exercises. | 05/11/2026 | 05/11/2026 | [Getting Started with AWS CloudShell - Using AWS CLI](https://000049.awsfcaj.com/3-useawscli/) |
| Friday | **Practice Cleaning Up and Deleting the CloudShell Environment After the Workshop**<br><br> - Learn about the purpose of cleaning up CloudShell resources and data after completing the practical exercises.<br> - Review the CloudShell environment and files created during the exercises, including the `project` directory and the `test.txt` and `test1.txt` files.<br> - Practice accessing the Actions menu in the AWS CloudShell interface.<br> - Select the Delete function to remove the CloudShell Environment according to the Workshop instructions.<br> - Confirm the deletion operation by clicking Delete in the confirmation dialog.<br> - Check the CloudShell Environment deletion process and complete the cleanup of the practical environment.<br> - Summarize the completed activities, including initializing CloudShell, using basic Linux commands, performing AWS CLI operations, and managing files.<br> - Recognize the importance of checking and managing data in the CloudShell environment after completing the Workshop. | 06/11/2026 | 06/11/2026 | [Getting Started with AWS CloudShell - Clean Up Resources](https://000049.awsfcaj.com/4-cleanup/) |

### Week 5 Achievements:

- Gained an overall understanding of AWS CloudShell and its role as a fully managed command-line environment provided by AWS, which can be accessed directly through the AWS Management Console without requiring additional installation or configuration on a personal computer.

- Understood the main benefits of AWS CloudShell in AWS administration, including:
  - Accessing a command-line environment directly through a web browser.
  - Using preinstalled AWS CLI and AWS SDKs.
  - Performing AWS resource management and inspection operations.
  - Supporting the creation and execution of automation scripts.
  - Providing 1 GB of storage allocated to the `$HOME` directory.

- Understood the authentication and access control mechanism of CloudShell through the permissions of the IAM User or IAM Role currently used in the AWS Management Console, allowing operations on AWS services according to the granted permissions.

- Practiced accessing AWS CloudShell through the AWS Management Console, searching for the CloudShell service, opening a CloudShell Environment, and becoming familiar with the Terminal interface.

- Learned how to use basic Linux commands in AWS CloudShell, including:
  - **`pwd`:** Displays the path of the current working directory.
  - **`ls -la`:** Lists files and directories, including hidden items and access permission information.
  - **`mkdir`:** Creates a new directory.
  - **`cd`:** Navigates between directories.
  - **`touch`:** Creates a new file.
  - **`vi`:** Opens and edits files using a text editor.
  - **`cat`:** Displays the contents of a file.

- Understood the meaning of Linux `rwx` permissions, including:
  - **Read (r):** Permission to read data.
  - **Write (w):** Permission to write and modify data.
  - **Execute (x):** Permission to execute files or access directories.
  - **User:** Permissions assigned to the file or directory owner.
  - **Group:** Permissions assigned to the user group.
  - **Other:** Permissions assigned to all other users.

- Gained practical experience in creating and managing directories and files in CloudShell through the following operations:
  - Created the `project` directory using the `mkdir` command.
  - Navigated into the directory using the `cd` command.
  - Created the `test.txt` file using the `touch` command.
  - Edited file contents using the `vi` text editor.
  - Saved changes and exited the editor using `Esc` and `:wq`.
  - Verified file contents using the `cat` command.

- Gained an overall understanding of AWS Command Line Interface (AWS CLI), including its role in managing and interacting with AWS services through command-line operations and supporting the automation of administrative tasks.

- Understood that AWS CLI is already installed and preconfigured in AWS CloudShell, eliminating the need for manual installation.

- Practiced using AWS CLI commands to check and retrieve AWS resource information, including:
  - **`aws --version`:** Checks the version of AWS CLI currently in use.
  - **`aws s3 ls`:** Lists Amazon S3 Buckets in the AWS account.
  - **`aws ec2 describe-instances`:** Retrieves information about EC2 Instances in the AWS account.

- Understood how AWS CLI uses the access permissions granted to the current IAM User or IAM Role to perform operations on AWS services.

- Gained practical experience in managing and transferring files between a personal computer and the CloudShell environment, including:
  - Created the `test.txt` file on a personal computer before uploading it to CloudShell.
  - Used Actions → Upload file to upload the file from the personal computer to CloudShell.
  - Used the `ls` command to verify that the file had been uploaded.
  - Used the `cat` command to check the file contents.
  - Created the `test1.txt` file directly in CloudShell.
  - Edited and saved the file contents using the `vi` text editor.
  - Used Actions → Download file to download the file from CloudShell to the personal computer.
  - Verified the file contents after the download was completed successfully.

- Understood the convenience of the Upload file and Download file features in CloudShell, which support data exchange between the AWS working environment and a personal computer without requiring additional external file transfer tools.

- Learned the process of cleaning up a CloudShell Environment after completing the Workshop, including:
  - Accessing the Actions menu in the CloudShell interface.
  - Selecting the Delete function.
  - Confirming the deletion by clicking Delete.
  - Completing the removal of the CloudShell Environment according to the instructions.

- Recognized the importance of managing the working environment, data, and AWS resources after completing practical exercises to avoid retaining unnecessary data and minimize unexpected costs.