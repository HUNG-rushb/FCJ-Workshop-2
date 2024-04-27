---
title: "Clean up resources"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

1. Access the **ECS** service, select the **FCJ_Cluster** cluster, go to **Services**, select **FCJ_Service**, then **Delete service** and confirm **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/1.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/2.png)

2. After deleting the service, select **Delete cluster** to delete the cluster, confirm and press **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/3.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/4.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/5.png)

3. Access the **CloudFormation** service, confirm that all stacks with names related to **FCJ_Cluster** have been successfully deleted.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/6.png)

4. Access the **CodePipeline** service, select the **FCJ_Pipeline** pipeline and **Delete pipeline**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/7.png)

5. Select **CodeCommit** on the left menu, select the **FCJ_Repo** repo and **Delete repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/8.png)

6. Select **CodeBuild** on the left menu, select the **FCJ_Build_Project** project, then select **Action** and **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/9.png)

7. Access the **S3** service, select the **codepipeline-...** bucket and delete the **FCJ_Pipeline** folder. You can choose to keep this bucket to deploy other pipelines later or completely delete this bucket.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/10.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/11.png)

8. Access the **ECR** service, select the **fcj_image_repo** repo and **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/18.png)

9. Access the **ECR** service, go to **Roles** and search for **`codebuild`**, select the **codebuild*FCJ*...** role and **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/12.png)

10. Access the **EC2** service, go to **Load balancers**, select **FCJ_ALB**, then **Actions** and **Delete load balancer**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/13.png)

11. Continue on the **EC2** console, go to **Target groups**, select **FCJ_TG**, then **Actions** and **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/14.png)

12. Access the **VPC** service, go to **Subnets**, select 3 subnets **fcj-subnet-...**, then **Actions** and **Delete subnet**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/15.png)

13. Continue on the **VPC** console, go to **Security groups**, select **FCJ_SG**, then **Actions** and **Delete security groups**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/16.png)

14. Access the **CloudWatch** service, go to **Log groups**, select group **aws/codebuild/FCJ_Build_Project**, then **Actions** and **Delete log group(s)**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/17.png)
