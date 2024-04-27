---
title: "Dọn dẹp tài nguyên"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

1. Truy cập dịch vụ **ECS**, chọn cluster **FCJ_Cluster**, vào phần **Services**, chọn **FCJ_Service**, sau đó **Delete service** và xác nhận **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/1.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/2.png)

2. Sau khi xóa service, chọn **Delete cluster** để xóa cluster, xác nhận và nhấn **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/3.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/4.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/5.png)

3. Truy cập dịch vụ **CloudFormation**, xác nhận những stack có tên liên quan đến **FCJ_Cluster** đều đã được xóa thành công.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/6.png)

4. Truy cập dịch vụ **CodePipeline**, chọn pipeline **FCJ_Pipeline** và **Delete pipeline**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/7.png)

5. Chọn **CodeCommit** ở menu bên trái, chọn repo **FCJ_Repo** và **Delete repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/8.png)

6. Chọn **CodeBuild** ở menu bên trái, chọn project **FCJ_Build_Project**, sau đó chọn **Action** và **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/9.png)

7. Truy cập dịch vụ **S3**, chọn bucket **codepipeline-...** và xóa folder **FCJ_Pipeline**. Bạn có thể chọn giữ lại bucket này để triển khai những pipeline khác sau này hoặc xóa hoàn toàn bucket này.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/10.png)

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/11.png)

8. Truy cập dịch vụ **ECR**, chọn repo **fcj_image_repo** và **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/18.png)

9. Truy cập dịch vụ **ECR**, vào **Roles** và tìm **`codebuild`**, chọn role **codebuild*FCJ*...** và **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/12.png)

10. Truy cập dịch vụ **EC2**, vào **Load balancers**, chọn **FCJ_ALB**, sau đó **Actions** và **Delete load balancer**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/13.png)

11. Tiếp tục trên console **EC2**, vào **Target groups**, chọn **FCJ_TG**, sau đó **Actions** và **Delete**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/14.png)

12. Truy cập dịch vụ **VPC**, vào **Subnets**, chọn 3 subnet **fcj-subnet-...**, sau đó **Actions** và **Delete subnet**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/15.png)

13. Tiếp tục trên console **VPC**, vào **Security groups**, chọn **FCJ_SG**, sau đó **Actions** và **Delete security groups**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/16.png)

14. Truy cập dịch vụ **CloudWatch**, vào **Log groups**, chọn group **aws/codebuild/FCJ_Build_Project**, sau đó **Actions** và **Delete log group(s)**.

![FCJ_ws2](/FCJ-Workshop-2/images/7.clean/17.png)
