---
title: "Create Security Group"
date: "`r Sys.Date()`"
weight: 3
chapter: true
pre: " <b> 2.3 </b> "
---

### Create Security Group

1. Go to **Security Groups** console, and choose **Create security group**.

![FCJ_ws2](/images/2.prerequisite/9.png)

2. Create security group:

- In the **Security group name** field, enter **`FCJ_SG`**.
- In the **Description** field, enter **`Allow inbound HTTP on port 80`**.
- In the **VPC** field, choose **Default VPC**.
- In the **Inbound rules** field, choose **Add rule**, **Type** choose **HTTP**, **Source** choose **Anywhere-IPv4**.
- Scroll down, and choose **Create security group** (not shown in the image).

  ![FCJ_ws2](/images/2.prerequisite/10.png)

