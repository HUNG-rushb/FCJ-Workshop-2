---
title: "Tạo private repo ECR"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

### Tạo private repo ECR

1. Di chuyển tới dịch vụ **Amazon Elastic Container Registry**. Tại menu bên trái, trong mục **Private registry**, chọn **Repositories**, sau đó chọn **Create repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_1.png)

2. Tiếp tục:

- Mục **Viability settings**, chọn **Private** (mặc định).
- Mục **Repository name**, nhập **`fcj-image-repo`**.
- Kéo xuống chọn **Create repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_2.png)

3. Xác nhận private image repo đã được tạo thành công.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_3.png)

4. Mở folder source code mà bạn đã tải về trong phần trước bằng IDE của bạn, sau đó:

- Mở file **buildspec.yml**, tại dòng 4, ECR_REPO_NAME, kiểm tra và thay thế tên repo **`fcj-image-repo`** bằng tên repo của bạn nếu bạn sử dụng tên khác, nếu không hãy giữ nguyên.
- Lưu lại file.

![FCJ_ws2](/FCJ-Workshop-2/images/3.codecommit/12.png)
