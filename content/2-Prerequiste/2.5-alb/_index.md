---
title: "Create Application Load Balancer"
date: "`r Sys.Date()`"
weight: 5
chapter: true
pre: " <b> 2.5 </b> "
---

### Create Application Load Balancer

1. Go to **Load balancers**, and choose **Create load balancer**.

![FCJ_ws2](/images/2.prerequisite/12.png)

2. Choose **Application Load Balancer**

![FCJ_ws2](/images/2.prerequisite/13.png)

3. \_

- In the **Load balancer name** field, enter **`FCJ-ALB`**.
- In the **Scheme** field, choose **Internet-facing** (default).
- In the **IP address type** field, choose **IPv4** (default).

![FCJ_ws2](/images/2.prerequisite/14.png)

4. In the **Network mapping** section:

- In the **VPC** field, choose **Default VPC**.
- In the **Mappings** field, tick all 3 **AZ**, then choose the corresponding **fcj-subnet** for each **AZ** that we have created.

![FCJ_ws2](/images/2.prerequisite/15.png)

5. In the **Security groups** section, open the dropdown, uncheck **default** and choose **FCJ-SG**.

![FCJ_ws2](/images/2.prerequisite/16.png)

![FCJ_ws2](/images/2.prerequisite/17.png)

6. In the **Listeners and routing** section, at **Default action**, choose target group **FCJ-TG**.

![FCJ_ws2](/images/2.prerequisite/18.png)

7. Check the configuration again.

![FCJ_ws2](/images/2.prerequisite/19.png)

8. Confirm that the ALB has been created successfully.

![FCJ_ws2](/images/2.prerequisite/20.png)