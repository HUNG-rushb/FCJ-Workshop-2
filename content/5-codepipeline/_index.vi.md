---
title: "AWS CodePipeline"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

**AWS CodePipeline** là dịch vụ continuous delivery mà bạn có thể sử dụng để lập mô hình, trực quan hóa và tự động hóa các bước cần thiết để deploy phần mềm của mình. Bạn có thể nhanh chóng thiết lập mô hình, xác định cấu hình các giai đoạn khác nhau của quy trình phát hành phần mềm. **CodePipeline** tự động hóa các bước cần thiết để liên tục deploy các thay đổi phần mềm.

1. Truy cập dịch vụ **AWS CodePipeline**. Ở menu bên trái, chọn **Pipelines**, sau đó **Create pipeline**.

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
