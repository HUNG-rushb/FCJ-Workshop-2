---
title: "Cập nhật Deploy stage"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 6.5 </b> "
---

### Cập nhật Deploy stage

1.  Truy cập tới dịch vụ **AWS CodePipeline**, chọn **FCJ_Pipeline** và chọn **Edit**.

![FCJ_ws2](/images/6.codedeploy/24.png)

2. Nhấn **Add stage** sau stage **Build**.

![FCJ_ws2](/images/6.codedeploy/25.png)

3. Nhập **Deploy** vào **Stage name** và nhấn **Add stage**.

![FCJ_ws2](/images/6.codedeploy/26.png)

4. Nhấn **Add action group** cho stage **Deploy**.

![FCJ_ws2](/images/6.codedeploy/27.png)

5. Thực hiện:

- Mục **Action name**, nhập **`DeployToECS`**.
- Mục **Action provider**, chọn **Amazon ECS (Blue/Green)**.
- Mục **Region**, chọn **US East (N. Virginia)**.
- Mục **Input artifacts**, chọn **BuildArtifact**.
- Mục **AWS CodeDeploy application name**, chọn application mà **ECS** đã tạo.
- Mục **AWS CodeDeploy deployment group**, chọn deployment group duy nhất.

![FCJ_ws2](/images/6.codedeploy/28.png)

6. Tiếp tục:

- Mục **Amazon ECS task definition**, chọn **BuildArtifact** và nhập **`taskdef.json`**.
- Mục **AWS CodeDeploy AppSpec file**, chọn **BuildArtifact** và nhập **`appspec.yaml`**.
- Mục **Input artifact with image details**, chọn **BuildArtifact**.
- Mục **Placeholder text in the task definition**, nhập **`IMAGE1_NAME`**.
- Nhấn **Done** (không có trong hình).

![FCJ_ws2](/images/6.codedeploy/29.png)

7. Nhấn **Done** để lưu stage.

![FCJ_ws2](/images/6.codedeploy/30.png)

8. Kéo lên trên cùng nhấn **Save** và xác nhận.

![FCJ_ws2](/images/6.codedeploy/31.png)

![FCJ_ws2](/images/6.codedeploy/32.png)

9. XÁc nhận pipeline đã có thêm stage **Deploy**, stage chưa được chạy vì chưa có gì trigger.

![FCJ_ws2](/images/6.codedeploy/33.png)
