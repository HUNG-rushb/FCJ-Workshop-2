---
title: "Create Task definition"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

### Create Task definition

1. Access to **AWS Elastic Container Service**, select **Task definitions**, then select **Create new task definition** continuously 2 times.

![FCJ_ws2](/images/6.codedeploy/4.png)

//translate below to english

2. In **Task definition family**, enter **`FCJ_Task_Definition`**.

![FCJ_ws2](/images/6.codedeploy/5.png)

3. In **Infrastructure requirements**, do:
- In **Launch type**, select **AWS Fargate**.
- In **Task size**, **CPU** select **.5 vCPU**, **Memory** select **2GB**.
- In **Task role**, select **ecsTaskExecutionRole**.
- In **Task execution role**, select **ecsTaskExecutionRole**.

![FCJ_ws2](/images/6.codedeploy/6.png)

4. Access **AWS ECR**, go to repo **fci_image_repo** and copy latest image URI as in the image.
   
![FCJ_ws2](/images/6.codedeploy/7.png)

5. In **Containner - 1**, do:
- In **Name**, enter **`fcj_container`**.
- In **Image URI**, paste the image URI you copied in step 4.

![FCJ_ws2](/images/6.codedeploy/8.png)

6. Confirm that the task definition has been created successfully.

![FCJ_ws2](/images/6.codedeploy/9.png)
