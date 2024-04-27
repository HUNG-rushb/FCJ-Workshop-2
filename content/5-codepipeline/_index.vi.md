---
title: "AWS CodePipeline"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

**AWS CodePipeline** là dịch vụ continuous delivery mà bạn có thể sử dụng để lập mô hình, trực quan hóa và tự động hóa các bước cần thiết để deploy phần mềm của mình. Bạn có thể nhanh chóng thiết lập mô hình, xác định cấu hình các giai đoạn khác nhau của quy trình phát hành phần mềm. **CodePipeline** tự động hóa các bước cần thiết để liên tục deploy các thay đổi phần mềm.

- **Rapid delivery** **CodePipeline** tự động hóa quy trình phát hành phần mềm của bạn, giúp bạn nhanh chóng phát hành các tính năng mới cho người dùng của bạn. Với **CodePipeline**, bạn có thể nhanh chóng lặp lại phản hồi và đưa các tính năng mới đến người dùng của bạn nhanh hơn.
- **Configurable workflow** **AWS CodePipeline** cho phép bạn mô hình các giai đoạn khác nhau của quy trình phát hành phần mềm của mình bằng cách sử dụng giao diện console, **AWS CLI**, **AWS CloudFormation**, hoặc **AWS SDKs**. Bạn có thể dễ dàng chỉ định các bài kiểm tra cần chạy và tùy chỉnh các bước để triển khai ứng dụng và các phụ thuộc của nó.
- **Get started fast** Với **CodePipeline**, bạn có thể ngay lập tức bắt đầu mô hình quy trình phát hành phần mềm của mình. Không có máy chủ nào cần cung cấp hoặc thiết lập. **CodePipeline** là dịch vụ continuous delivery được quản lý hoàn toàn kết nối với các công cụ và hệ thống hiện có của bạn.
- **Easy to integrate** **AWS CodePipeline** có thể dễ dàng mở rộng để phù hợp với nhu cầu cụ thể của bạn. Bạn có thể sử dụng các plugin được xây dựng sẵn của AWS hoặc plugin tùy chỉnh của riêng bạn trong bất kỳ bước nào của quy trình phát hành của mình. Ví dụ, bạn có thể kéo mã nguồn của mình từ GitHub hoặc sử dụng máy chủ xây dựng Jenkins on-premises của mình. Bạn có thể chạy các bài kiểm tra tải bằng dịch vụ bên thứ ba hoặc chuyển thông tin triển khai đến bảng điều khiển vận hành tùy chỉnh của bạn.

Tự động hóa quy trình xây dựng, kiểm tra và phát hành của bạn giúp bạn kiểm tra mỗi thay đổi mã nguồn một cách nhanh chóng và dễ dàng và phát hiện lỗi khi chúng còn nhỏ và dễ sửa. Bạn có thể đảm bảo chất lượng của mã ứng dụng hoặc cơ sở hạ tầng của mình bằng cách chạy mỗi thay đổi qua quy trình staging và phát hành của mình.

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
