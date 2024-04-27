---
title: "Creat Cluster service"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 6.4 </b> "
---

### Create Cluster service

1. Access to **AWS ECS**, select **Clusters**, and choose the cluster **FCJ_Cluster**.

![FCJ_ws2](/images/6.codedeploy/10.png)

2. Choose **Create** in the **Services** tab.

![FCJ_ws2](/images/6.codedeploy/11.png)

3. In **Compute options**, choose **Launch type**, and select **Fargate** (default), **Platform version** is **LATEST**.

![FCJ_ws2](/images/6.codedeploy/12.png)

4. At **Deployment configuration**:

- In **Application type**, choose **Service**.
- In **Family**, choose **FCJ_Task_Definition**, **Revision** automatically selects the **LATEST** version.
- In **Project name**, choose **FCJ_Build_Project**.
- In **Service name**, enter **`FCJ_Service`**.
- In **Desired tasks**, enter **`3`**.

![FCJ_ws2](/images/6.codedeploy/13.png)

5. Continue:

- In **Deployment options**, choose **Blue/green deployment (powered by AWS CodeDeploy)**.
- In **Deployment configuration**, choose **CodeDeployDefault.ECSLinear10PercentEvery1Minutes**.
- In **Service role for CodeDeploy**, choose **CodeDeployServiceRole**.

![FCJ_ws2](/images/6.codedeploy/14.png)

6. In **Networking**:

- In **VPC**, choose **Default VPC**.
- In **Subnets**, choose 3 public subnets **fcj-subnet-...**.
- In **Security group**, choose **Use an existing security group**, then add **FCJ_SG**, there will be 2 security groups as shown in the image.
- In **Public IP**, choose **Turned on**.

![FCJ_ws2](/images/6.codedeploy/15.png)

7. In **Load balancing**:

- In **Load balancer type**, choose **Application Load Balancer**.
  - In **Application Load Balancer**, choose **Use an existing load balancer**.
  - In **Load balancer**, choose **FCJ_ALB**.
  - In **Health check grace periodInfo**, enter **`0`**.

![FCJ_ws2](/images/6.codedeploy/16.png)

8. Continue:

- In **Listeners** and  **Production listener**, choose **Use an existing listener** and select **80:HTTP**.
- Check target group is **FCJ_TG**.

![FCJ_ws2](/images/6.codedeploy/17.png)

9. In **Target groups**:

- In **Application type**, choose **Service**.
- In **Target group 1**, choose **Use an existing target group** and then choose **FCJ_TG** in the dropdown on the right.
- In **Target group 2**, choose **Create new target group**.
- In **Target group 2 name**, enter **`FCJ-TG-Blue`**.
- Then scroll down to the bottom and choose **Create** (not in the image).

![FCJ_ws2](/images/6.codedeploy/18.png)

//translate below to english

10. Access to **AWS CloudFormation**, we will see a new stack being created, this is the stack that contains our service.

![FCJ_ws2](/images/6.codedeploy/19.png)

11.  After the stack is created successfully, access the **AWS CodeDeploy** service, go to **Applications**, we will see an application in the form of **AppECS-...**. This is the application that **ECS** uses to deploy the application. Click on the application to observe.

![FCJ_ws2](/images/6.codedeploy/19_1.png)

12.  Choose the **Deployment groups** tab, select the only deployment group in it, and choose **Edit**.

![FCJ_ws2](/images/6.codedeploy/19_2.png)

13.  Scroll down to the bottom, in the **Deployment settings** section, change the **Original revision termination** time to **0 hour 15 minutes** as shown in the image. Press **Save changes**.

![FCJ_ws2](/images/6.codedeploy/19_3.png)

14.  Return to the **ECS** console, check the **Services** of the cluster, we will see **FCJ_Service** running successfully.

![FCJ_ws2](/images/6.codedeploy/20.png)

15.  Switch to the **Tasks** tab, we will see 3 tasks **Running**.

![FCJ_ws2](/images/6.codedeploy/21.png)

16.  Access the **AWS EC2** service, go to **Load balancers**, select **FCJ_ALB** and copy the **DNS Name**.
![FCJ_ws2](/images/6.codedeploy/22.png)

17. Access the DNS address of the ALB, we will be directed to the **Fargate container** hosting the Calculator application. **Note that you will have to connect via HTTP**.

![FCJ_ws2](/images/6.codedeploy/23.png)
