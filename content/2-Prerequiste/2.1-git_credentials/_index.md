---
title: "Create HTTPS Git Credentials for CodeCommit"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

With Git credentials, you can create a username and static password in the IAM Console that you can use to access **AWS CodeCommit** from the command line, Git CLI, or any Git tool that supports HTTPS authentication.

Because these are static credentials, they can be cached using password management tools available in your local operating system or stored in a credential management utility. This allows you to get started with AWS CodeCommit in minutes. You don't need to download the AWS CLI or configure Git client applications to connect to **CodeCommit** repositories over HTTPS. You can also use the username and password to connect to **CodeCommit** from third-party tools that support username and password authentication, including popular Git GUI client applications (such as TowerUI) and IDEs (such as Eclipse, IntelliJ, and Visual Studio).

### Create HTTPS Git Credentials for CodeCommit

1. From the root account, access the IAM console of the IAM account you will use for this lab, choose **Security credentials**.

![FCJ_ws2](/images/2.prerequisite/_1.png)

2. In the **HTTPS Git credentials for AWS CodeCommit** section, choose **Generate credentials**

![FCJ_ws2](/images/2.prerequisite/_2.png)

3. Choose **Download credentials**, and save it where you can easily access it again.

![FCJ_ws2](/images/2.prerequisite/_3.png)
