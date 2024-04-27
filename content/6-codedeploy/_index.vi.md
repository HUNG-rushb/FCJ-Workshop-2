---
title: "AWS CodeDeploy và AWS ECS"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/aws_codedeploy.png)

**CodeDeploy** là một dịch vụ triển khai tự động ứng dụng đến các instance **Amazon EC2**, instance on-premises, hàm serverless **Lambda**, hoặc dịch vụ **Amazon ECS**.

- **Triển khai tự động** **AWS CodeDeploy** hoàn toàn tự động hóa việc triển khai phần mềm của bạn, giúp bạn triển khai một cách đáng tin cậy và nhanh chóng. Bạn có thể triển khai ứng dụng của mình một cách nhất quán trên môi trường phát triển, thử nghiệm và sản xuất của bạn, dù triển khai đến **Amazon EC2**, **Fargate**, **Lambda**, hoặc máy chủ on-premises của bạn. Dịch vụ mở rộng với cơ sở hạ tầng của bạn.
- **Giảm thiểu thời gian chết** **AWS CodeDeploy** giúp tối đa hóa sẵn có của ứng dụng của bạn trong quá trình triển khai phần mềm. Nó giới thiệu các thay đổi một cách từ từ và theo dõi sức khỏe ứng dụng theo các quy tắc có thể cấu hình. Việc triển khai phần mềm có thể dễ dàng bị dừng lại và quay trở lại nếu có lỗi.
- **Kiểm soát tập trung** - **AWS CodeDeploy** cho phép bạn dễ dàng khởi chạy và theo dõi trạng thái của các triển khai ứng dụng của bạn thông qua **AWS Management Console** hoặc **AWS Command Line Interface (AWS CLI)**. **CodeDeploy** cung cấp cho bạn một báo cáo chi tiết giúp bạn xem khi nào và đến đâu mỗi bản sửa đổi ứng dụng đã được triển khai. Bạn cũng có thể tạo thông báo đẩy để nhận cập nhật trực tiếp về các triển khai của bạn.
- **Dễ áp dụng** - **AWS CodeDeploy** không phụ thuộc vào nền tảng và ngôn ngữ, hoạt động với bất kỳ ứng dụng nào, và cung cấp trải nghiệm giống nhau dù bạn đang triển khai đến **Amazon EC2**, **Fargate**, hoặc **Lambda**. Bạn có thể dễ dàng tái sử dụng mã cài đặt hiện có của mình. **CodeDeploy** cũng có thể tích hợp với quy trình phát hành phần mềm hiện có của bạn hoặc chuỗi công cụ phát triển liên tục (ví dụ: **CodePipeline**, **GitHub**, **Jenkins**).

### Nội dung

1.  [Tạo ECS Cluster](6.1-cluster/)
2.  [Tạo Task definition](6.2-task_def)
3.  [Cập nhật code](6.3-code/)
4.  [Tạo Cluster service](6.4-service/)
5.  [Cập nhật Deploy stage](6.5-deploy_stage/)
6.  [Cập nhật và quan sát deployment](6.6-deployment/)
