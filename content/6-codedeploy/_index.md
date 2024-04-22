---
title: "AWS CodeDeploy and AWS ECS"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

![FCJ_ws2](/images/6.codedeploy/aws_codedeploy.png)

**CodeDeploy** is a deployment service that automates application deployments to **Amazon EC2** instances, on-premises instances, serverless **Lambda** functions, or **Amazon** ECS services.

- **Automated deployments** **AWS CodeDeploy** fully automates your software deployments, enabling you to deploy reliably and rapidly. You can consistently deploy your application across your development, test, and production environments whether deploying to **Amazon EC2**, **Fargate**, **Lambda**, or your on-premises servers. The service scales with your infrastructure.
- **Minimize downtime** **AWS CodeDeploy** helps maximize your application availability during the software deployment process. It introduces changes incrementally and tracks application health according to configurable rules. Software deployments can easily be stopped and rolled back if there are errors.
- **Centralized control** - **AWS CodeDeploy** enables you to easily launch and track the status of your application deployments through the **AWS Management Console** or the **AWS Command Line Interface (AWS CLI)**. **CodeDeploy** gives you a detailed report enabling you to view when and to where each application revision was deployed. You can also create push notifications to receive live updates about your deployments.
- **Easy to adopt** - **AWS CodeDeploy** is platform and language agnostic, works with any application, and provides the same experience whether you’re deploying to **Amazon EC2**, **Fargate**, or **Lambda**. You can easily reuse your existing setup code. **CodeDeploy** can also integrate with your existing software release process or continuous delivery toolchain (e.g., **CodePipeline**, **GitHub**, **Jenkins**).

### Content

1.  [Create ECS Cluster](6.1-cluster/)
2.  [Create Task definition](6.2-task_def)
3.  [Update code](6.3-code/)
4.  [Create Cluster service](6.4-service/)
5.  [Update Deploy stage](6.5-deploy_stage/)
6.  [Update và monitor deployment](6.6-deployment/)
