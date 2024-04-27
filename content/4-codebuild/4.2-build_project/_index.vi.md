---
title: "Tạo CodeBuild project"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Tạo CodeBuild project

1. Di chuyển tới dịch vụ **CodeBuild**, ở menu bên trái chọn **Build projects**, sau đó chọn **Create project**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/1.png)

2. Sau đó:

- Mục **Project name**, nhập **`FCJ_Build_Project`**.
- Mục **Source 1 - Primary**, chọn provider **AWS CodeCommit**, sau đó chọn repo **FCJ_Repo**.
- Mục **Branch**, chọn **master**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/2.png)

3. Mở mục **Additional configuration**, sau đó tick chọn **Enable this flag if you want to build Docker images or want your builds to get elevated privileges**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/3.png)

4. Mục **Buildspec**, tick chọn **Use a buildspec file**, nhập **`buildspec.yml`**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/4.png)

5. Kéo xuống dưới và chọn **Create build project**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/5.png)

6. Xác nhận build project đã được tạo thành công.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/6.png)
