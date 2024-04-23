---
title: "AWS CodePipeline"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

![FCJ_ws2](/images/5.codepipeline/aws_codepipeline.png)

**AWS CodePipeline** is a continuous delivery service you can use to model, visualize, and automate the steps required to release your software. You can quickly model and configure the different stages of a software release process. **CodePipeline** automates the steps required to release your software changes continuously.

- **Rapid delivery** **CodePipeline** automates your software release process, enabling you to rapidly release new features to your users. With **CodePipeline**, you can quickly iterate on feedback and get new features to your users faster.
- **Configurable workflow** **AWS CodePipeline** enables you to model the different stages of your software release process using the console interface, the **AWS CLI**, **AWS CloudFormation**, or the **AWS SDKs**. You can easily specify the tests to run and customize the steps to deploy your application and its dependencies.
- **Get started fast** With **CodePipeline**, you can immediately begin to model your software release process. There are no servers to provision or set up. **CodePipeline** is a fully managed continuous delivery service that connects to your existing tools and systems.
- **Easy to integrate** **AWS CodePipeline** can easily be extended to adapt to your specific needs. You can use AWS pre-built plugins or your own custom plugins in any step of your release process. For example, you can pull your source code from GitHub or use your on-premises Jenkins build server. You can run load tests using a third-party service or pass on deployment information to your custom operations dashboard.

Automating your build, test, and release process enables you to quickly and easily test each code change and catch bugs while they are small and simple to fix. You can ensure the quality of your application or infrastructure code by running each change through your staging and release process.

### Create pipeline

1. Truy cập dịch vụ \***\*AWS CodePipeline\*\***. Ở menu bên trái, chọn **Pipelines**, sau đó **Create pipeline**.

![FCJ_ws2](/images/5.codepipeline/1.png)

2. Mục **Pipeline name**, nhập **`FCJ_Pipeline`**. Các lựa chọn khác giữ nguyên mặc định như hình.

![FCJ_ws2](/images/5.codepipeline/2.png)

3. Mục **Advanced settings**, **Artifact store** chọn **Default location** và **Encryption key** chọn **Default AWS Managed key**. Ấn **Next**.

![FCJ_ws2](/images/5.codepipeline/3.png)

4. Tiếp tục:

- Mục **Source provider**, chọn **AWS CodeCommit**.
- Mục **Repository name**, chọn **FCJ_Repo**.
- Mục **Branch name**, chọn **master**.
- Còn lại giữ nguyên mặc định, sau đó nhấn **Next**.

![FCJ_ws2](/images/5.codepipeline/4.png)

5. Click vào account góc phía trên cùng bên phải, sau đó copy **Account ID** của bạn.

![FCJ_ws2](/images/5.codepipeline/5.png)

6. Tiếp tục:

- Mục **Build provider**, chọn **AWS CodeBuild**.
- Mục **Region**, chọn **US East**.
- Mục **Project name**, chọn **FCJ_Build_Project**.
- Nhấn **Add enviroment variable**. Mục **Name**, nhập **`AWS_ACCOUNT_ID`**. Mục **Value** hãy paste vào Account ID mà bạn đã copy trước đó.
- Còn lại giữ nguyên mặc định, sau đó nhấn **Next**.

![FCJ_ws2](/images/5.codepipeline/6.png)

7. Nhấn **Skip deploy stage**, xác nhận **Skip** khi popup hiện ra.

![FCJ_ws2](/images/5.codepipeline/7.png)

8. Kiếm tra lại cấu hình và nhấn **Create pipeline**.

![FCJ_ws2](/images/5.codepipeline/8.png)

9. Xác nhận pipeline đã được tạo thành công. Chờ cho đến khi pipeline build thành công như trong hình.

![FCJ_ws2](/images/5.codepipeline/9.png)

10. Truy cập tới dịch vụ **AWS ECR**, vào repo **fcj-image-repo** và xác nhận đã có 1 image được build và store thành công.

![FCJ_ws2](/images/5.codepipeline/10.png)
