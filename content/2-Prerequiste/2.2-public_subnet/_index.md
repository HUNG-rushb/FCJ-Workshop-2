---
title: "Create Public Subnet"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

1. Go to **VPC** console, and check if you have **Default VPC** or not.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/2.png)

2. Choose **Subnets** in the navigation pane on the left, and then choose **Create subnet**.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/3.png)

3. Choose **Default VPC**.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/4.png)

4. Create subnet 1:

- In the **Subnet name** field, enter **`fcj-subnet-1`**.
- In the **Availability zone** field, choose **`us-east-1a`**.
- In the **IPv4 subnet CIDR block** field, enter **`172.31.200.0/24`**.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/5.png)

5. Choose **Add new subnet**, and create subnet 2:

- In the **Subnet name** field, enter **`fcj-subnet-2`**.
- In the **Availability zone** field, choose **`us-east-1b`**.
- In the **IPv4 subnet CIDR block** field, enter **`172.31.201.0/24`**.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/6.png)

6. Choose **Add new subnet**, and create subnet 3:

- In the **Subnet name** field, enter **`fcj-subnet-3`**.
- In the **Availability zone** field, choose **`us-east-1c`**.
- In the **IPv4 subnet CIDR block** field, enter **`172.31.202.0/24`**.
- Choose **Create subnet**.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/7.png)

7. Confirm that 3 subnets have been created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/2.prerequisite/8.png)
