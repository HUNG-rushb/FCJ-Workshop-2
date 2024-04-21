---
title: "Update code"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 6.3 </b> "
---

### Cập nhật code

1. Truy cập **AWS ECS**, vào **Task definitions**, và chọn task **FCJ_Task_Definition** mà ta đã tạo. Chọn tab **JSON**, sau đó **Copy to clipboard**.

![FCJ_ws2](/images/6.codedeploy/9_1.png)

2. Từ source code, mở file **`taskdef.json`** trong IDE của bạn. Thay thế toàn bộ nội dung trong file đó bằng task definition mà bạn đã copy bước 1.

![FCJ_ws2](/images/6.codedeploy/9_2.png)

3. Tại dòng số 6, nơi có key **image**, thay thế value của nó bằng **`<IMAGE1_NAME>`**.

![FCJ_ws2](/images/6.codedeploy/9_3.png)

4. Kéo xuống cuối hoặc search trong IDE cụm từ **`tags`**, bạn sẽ tìm thấy **"tags": []**, hãy xóa nó đi.

![FCJ_ws2](/images/6.codedeploy/9_4.png)

5. Mở file **`appspec.yml`**, tại dòng số 8, **ContainerName**, thay thế value bằng **`fcj_container`**. Đây chính là tên container mà bạn đã đặt trong bước **5** phần **6.2**, bạn cũng có thể tìm thấy **"name": "fcj_container"** trong task definition ở file **`taskdef.json`**.

![FCJ_ws2](/images/6.codedeploy/9_5.png)

6. Thực hiện đẩy code lên repo:

- Chạy **`git add .`**.
- Chạy **`git commit -m "Update config"`** để commit code trên local.
- Chạy **`git push origin master`** để đẩy code lên repo trên **CodeCommit**.

![FCJ_ws2](/images/6.codedeploy/9_6.png)

7. Hãy mở pipeline của bạn và quan sát. Sau khi tất cả các stage thành công, hãy truy cập **AWS S3**, tìm và chọn bucket **codepipeline-us-east-1-......**. Đây là bucket được **CodePipeline** tạo ra để lưu artifact. Mỗi region sẽ có 1 bucket tương ứng với region của pipeline.

![FCJ_ws2](/images/6.codedeploy/9_7.png)

8. Chọn folder có tên pipeline **`FCJ_Pipeline`**.

![FCJ_ws2](/images/6.codedeploy/9_8.png)

9. Chọn folder **`BuildArtif`**.

![FCJ_ws2](/images/6.codedeploy/9_9.png)

10. Nhấn vào tab **Last modified** để sắp xếp theo thời gian, chọn vào item gần đây nhất, nhấn **Download** để tải về.

![FCJ_ws2](/images/6.codedeploy/9_10.png)

11. Giải nén và kiểm tra xác nhận nội dung đã đúng với những gì bạn đã chỉnh sửa ở các bước trên. Nếu vậy thì artifact của chúng ta đã được build thành công.

![FCJ_ws2](/images/6.codedeploy/9_11.png)
