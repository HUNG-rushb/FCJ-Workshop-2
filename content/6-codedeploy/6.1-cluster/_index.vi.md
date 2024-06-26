---
title: "Tạo ECS Cluster"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 6.1 </b> "
---

### Tạo Role cho ECS task

1. Truy cập dịch vụ **IAM**, chọn **Roles** tại menu bên trái, chọn **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/101.png)

2. Tiếp tục:

- Mục **Trusted entity type**, chọn **AWS Service**.
- Mục **Use case**, chọn **`Elastic Container Service`**, sau đó chọn **Elastic Container Service Task**.
- Nhấn **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/102.png)

3. Continue:

- Mục **Permissions policies**, nhập `AmazonECSTaskExecutionRolePolicy` để tìm và chọn.
- Nhấn **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/103.png)

4. Nhập tên `ecsTaskExecutionRole`.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/104.png)

5. Kiểm tra policy và nhấn **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/105.png)

6. Xác nhận tạo role thành công.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/106.png)

### Tạo CodeDeploy Role cho ECS

7. Tiếp tục chọn **Create role**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/201.png)

8. Tiếp tục:

- Mục **Trusted entity type**, chọn **AWS Service**.
- Mục **Use case**, chọn **`CodeDeploy`**, sau đó chọn **CodeDeploy - ECS**.
- Nhấn **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/202.png)

9. Xác nhận đã có policy **AWSCodeDeployRoleForECS**. Nhấn **Next**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/203.png)

10. Nhập tên `CodeDeployServiceRole`. Kiểm tra policy và nhấn **Create role** (cuối trang).

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/204.png)

11. Xác nhận tạo role thành công.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/205.png)

### Tạo ECS Cluster

12. Truy cập tới dịch vụ **AWS Elastic Container Service**, chọn **Create cluster**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/1.png)

13. Mục **Cluster name**, nhập **`FCJ_Cluster`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/2.png)

14. Xác nhận cluster đã được tạo thành công

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/3.png)
