---
title: "AWS Pipeline"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Triển khai CI/CD pipeline trên AWS

### Tổng quan

Trong workshop này, chúng ta sẽ cùng nhau xây dựng một CD pipeline sử dụng **AWS CodePipeline**.

![FCJ_ws2](/images/1.introduce/1.png)
![FCJ_ws2](/images/1.introduce/1.png?w=500)
![FCJ_ws2](/images/1.introduce/1.png?w=5)

**AWS CodePipeline** là dịch vụ continuous delivery mà bạn có thể sử dụng để lập mô hình, trực quan hóa và tự động hóa các bước cần thiết để deploy phần mềm của mình. Bạn có thể nhanh chóng thiết lập mô hình, xác định cấu hình các giai đoạn khác nhau của quy trình phát hành phần mềm. **CodePipeline** tự động hóa các bước cần thiết để liên tục deploy các thay đổi phần mềm.

### Nội dung

1.  [Giới thiệu](1-Introduce/)
2.  [Các bước chuẩn bị](2-Prerequiste/)
3.  [S3 Server Access Logging](3-s3sal/)
4.  [Sử dụng AWS CloudTrail](4-s3cloudtrail/)
5.  [Truy vấn log với AWS Athena](5-s3athena/)
6.  [Dọn dẹp tài nguyên](6-cleanup/)
