---
title: "Update Deploy stage"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 6.5 </b> "
---

### Update Deploy stage

1. Access **AWS CodePipeline**, select **FCJ_Pipeline**, and choose **Edit**.

![FCJ_ws2](/images/6.codedeploy/24.png)

2. Click **Add stage** after the **Build** stage.

![FCJ_ws2](/images/6.codedeploy/25.png)

3. Enter **Deploy** into **Stage name** and click **Add stage**.

![FCJ_ws2](/images/6.codedeploy/26.png)

4. Click **Add action group** for the **Deploy** stage.

![FCJ_ws2](/images/6.codedeploy/27.png)

5. Perform:

- In **Action name**, enter **`DeployToECS`**.
- In **Action provider**, choose **Amazon ECS (Blue/Green)**.
- In **Region**, choose **US East (N. Virginia)**.
- In **Input artifacts**, choose **BuildArtifact**.
- In **AWS CodeDeploy application name**, choose the application that **ECS** has created.
- In **AWS CodeDeploy deployment group**, choose the unique deployment group.

![FCJ_ws2](/images/6.codedeploy/28.png)

6. Continue:

- In **Amazon ECS task definition**, choose **BuildArtifact** and enter **`taskdef.json`**.
- In **AWS CodeDeploy AppSpec file**, choose **BuildArtifact** and enter **`appspec.yaml`**.
- In **Input artifact with image details**, choose **BuildArtifact**.
- In **Placeholder text in the task definition**, enter **`IMAGE1_NAME`**.
- Click **Done** (not shown in the image).

![FCJ_ws2](/images/6.codedeploy/29.png)

7. Click **Done** to save the stage.

![FCJ_ws2](/images/6.codedeploy/30.png)

8. Scroll to the top and click **Save** and confirm.

![FCJ_ws2](/images/6.codedeploy/31.png)

![FCJ_ws2](/images/6.codedeploy/32.png)

9. Confirm the pipeline has added the **Deploy** stage, the stage has not run because there is no trigger.

![FCJ_ws2](/images/6.codedeploy/33.png)