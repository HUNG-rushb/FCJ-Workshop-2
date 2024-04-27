---
title: "Tạo Task definition"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

### Tạo Task definition

1. Truy cập tới dịch vụ **AWS Elastic Container Service**, chọn **Task definitions**, sau đó chọn **Create new task definition** liên tục 2 lần.

![FCJ_ws2](/images/6.codedeploy/4.png)

2. Mục **Task definition family**, nhập **`FCJ_Task_Definition`**.

![FCJ_ws2](/images/6.codedeploy/5.png)

3. Mục **Infrastructure requirements**, thực hiện:

- Mục **Launch type**, chọn **AWS Fargate**.
- Mục **Task size**, **CPU** chọn **.5 vCPU**, **Memory** chọn **2GB**.
- Mục **Task role**, chọn **ecsTaskExecutionRole**.
- Mục **Task execution role**, chọn **ecsTaskExecutionRole**.

![FCJ_ws2](/images/6.codedeploy/6.png)

4. Truy cập **AWS ECR**, vào repo **fci_image_repo** và copy latest image URI như trong hình.

![FCJ_ws2](/images/6.codedeploy/7.png)

5. Mục **Containner - 1**, thực hiện:

- Mục **Name**, nhập **`fcj_container`**.
- Mục **Image URI**, paste vào image URI mà bạn đã copy ở bước 4.

![FCJ_ws2](/images/6.codedeploy/8.png)

6. Xác nhận task definition đã được tạo thành công.

![FCJ_ws2](/images/6.codedeploy/9.png)
