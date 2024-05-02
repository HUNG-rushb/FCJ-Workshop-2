---
title: "Create ECS Cluster"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 6.1 </b> "
---

### Create role for ECS task

1. Access **IAM** service, choose **Roles** on left panel, then choose **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/101.png)

2. Continue:

- For **Trusted entity type**, choose **AWS Service**.
- For **Use case**, choose **`Elastic Container Service`**, then choose **Elastic Container Service Task**.
- Click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/102.png)

3. Continue:

- For **Permissions policies**, input `AmazonECSTaskExecutionRolePolicy` to find and choose it.
- Click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/103.png)

4. Input name `ecsTaskExecutionRole`.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/104.png)

5. Check policies again and click **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/105.png)

6. Cofirm role created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/106.png)

### Create CodeDeploy Role for ECS

7. Continue, click **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/201.png)

8. Continue:

- For **Trusted entity type**, choose **AWS Service**.
- For **Use case**, choose **`CodeDeploy`**, then choose **CodeDeploy - ECS**.
- Click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/202.png)

9. Confirm policy **AWSCodeDeployRoleForECS**. Click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/203.png)

10. Type in `CodeDeployServiceRole` for name. Check everything again and click **Create role** (end of page).

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/204.png)

11. Cofirm role created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/205.png)

### Create ECS Cluster

12. Access the **AWS Elastic Container Service** service, then choose **Create cluster**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/1.png)

13. In the **Cluster name** field, enter **`FCJ_Cluster`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/2.png)

14. Confirm that the cluster has been created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/3.png)
