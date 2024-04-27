---
title: "AWS CodePipeline"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/aws_codepipeline.png)

**AWS CodePipeline** is a continuous delivery service you can use to model, visualize, and automate the steps required to release your software. You can quickly model and configure the different stages of a software release process. **CodePipeline** automates the steps required to release your software changes continuously.

- **Rapid delivery** **CodePipeline** automates your software release process, enabling you to rapidly release new features to your users. With **CodePipeline**, you can quickly iterate on feedback and get new features to your users faster.
- **Configurable workflow** **AWS CodePipeline** enables you to model the different stages of your software release process using the console interface, the **AWS CLI**, **AWS CloudFormation**, or the **AWS SDKs**. You can easily specify the tests to run and customize the steps to deploy your application and its dependencies.
- **Get started fast** With **CodePipeline**, you can immediately begin to model your software release process. There are no servers to provision or set up. **CodePipeline** is a fully managed continuous delivery service that connects to your existing tools and systems.
- **Easy to integrate** **AWS CodePipeline** can easily be extended to adapt to your specific needs. You can use AWS pre-built plugins or your own custom plugins in any step of your release process. For example, you can pull your source code from GitHub or use your on-premises Jenkins build server. You can run load tests using a third-party service or pass on deployment information to your custom operations dashboard.

Automating your build, test, and release process enables you to quickly and easily test each code change and catch bugs while they are small and simple to fix. You can ensure the quality of your application or infrastructure code by running each change through your staging and release process.

1. Access the **AWS CodePipeline** service. In the left menu, select **Pipelines**, then **Create pipeline**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/1.png)

2. In the **Pipeline name** field, enter **`FCJ_Pipeline`**. Keep the other options as default.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/2.png)

3. In the **Advanced settings**, **Artifact store** select **Default location** and **Encryption key** select **Default AWS Managed key**. Click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/3.png)

4. Continue:

- In the **Source provider**, select **AWS CodeCommit**.
- In the **Repository name**, select **FCJ_Repo**.
- In the **Branch name**, select **master**.
- Keep the rest as default, then click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/4.png)

5. Click on the account in the top right corner, then copy your **Account ID**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/5.png)

6. Continue:

- In the **Build provider**, select **AWS CodeBuild**.
- In the **Region**, select **US East**.
- In the **Project name**, select **FCJ_Build_Project**.
- Click **Add enviroment variable**. In the **Name**, enter **`AWS_ACCOUNT_ID`**. In the **Value** paste the Account ID you copied earlier.
- Keep the rest as default, then click **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/6.png)

7. Hit **Skip deploy stage**, confirm **Skip** when the popup appears.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/7.png)

8. Check the configuration again and click **Create pipeline**.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/8.png)

9. Confirm the pipeline has been created successfully. Wait until the pipeline builds successfully as shown in the image.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/9.png)

10. Access the **AWS ECR** service, go to the **fcj-image-repo** repo and confirm that an image has been built and stored successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/5.codepipeline/10.png)
