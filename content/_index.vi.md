---
title: "AWS Blue/Green Deployment"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Triển khai Blue/Green pipeline trên nền tảng AWS

### Tổng quan

Trong workshop này, chúng ta sẽ cùng nhau xây dựng một CD pipeline sử dụng **AWS CodePipeline**.

![FCJ_ws2](/images/1.introduce/1.png)

**AWS CodePipeline** là dịch vụ continuous delivery mà bạn có thể sử dụng để lập mô hình, trực quan hóa và tự động hóa các bước cần thiết để deploy phần mềm của mình. Bạn có thể nhanh chóng thiết lập mô hình, xác định cấu hình các giai đoạn khác nhau của quy trình phát hành phần mềm. **CodePipeline** tự động hóa các bước cần thiết để liên tục deploy các thay đổi phần mềm.

### Nội dung

1.  [Giới thiệu](1-Introduce/)
2.  [Các bước chuẩn bị](2-Prerequiste/)
3.  [AWS CodeCommit](3-codecommit/)
4.  [AWS CodeBuild](4-codebuild/)
5.  [AWS CodeDeploy và AWS ECS](5-codedeploy/)
6.  [AWS CodePipeline](6-codepipeline/)
7.  [Dọn dẹp tài nguyên](7-cleanup/)
