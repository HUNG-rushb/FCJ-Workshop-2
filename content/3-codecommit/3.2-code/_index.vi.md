---
title: "Push code lên repo"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

### Tải về source code

1. Truy cập vào https://github.com/HUNG-rushb/React-Calculator/releases/tag/v1 và tải về source code. Đây là Calculator App đơn giản được viết bằng React và chúng ta sẽ dùng để deploy.

![FCJ_ws2](/images/3.codecommit/5.png)

2. Tải về và giải nén nó trong thư mục mà bạn muốn làm việc. Kiểm tra các file có đầy đủ đủ giống như hình bên dưới hay không.

![FCJ_ws2](/images/3.codecommit/6.png)

### Push code lên CodeCommit repo

3. Bên trong thư mục đó:

- Chạy **`git init`** để tạo git repo.
- Chạy **`git remote add origin PASTE_HTTPS_REPO_LINK_HERE`**, thay thế **PASTE_HTTPS_REPO_LINK_HERE** bằng link HTTPS mà bạn đã copy ở phần trước.
- Chạy **`git add .`**.
- Chạy **`git commit -m "init"`** để commit code trên local (không có trong hình).

![FCJ_ws2](/images/3.codecommit/7.png)

4. Tiếp tục:

- Chạy **`git push origin master`** để đẩy code lên repo trên **CodeCommit**.
- Git sẽ hỏi bạn về **Username** và **Password**, đây chính là credentials trong file codecommit credentials mà ta đã tạo ở phần **Tạo HTTPS Git Credentials cho CodeCommit**.
- Mở file credentials lên, copy **username** và **password** vào cmd.
- Enter và xác nhận code đã được push lên thành công.

![FCJ_ws2](/images/3.codecommit/9.png)

5. Trở về tab mà bạn đang mở **AWS**, di chuyển tới dịch vụ **CodeCommit** và vào repo của bạn, bạn sẽ thấy code đã được push lên thành công.

![FCJ_ws2](/images/3.codecommit/10.png)

6. Trên menu bên trái, chọn **Commits** và kiểm tra commit gần nhất là của bạn, trong hình là **init**.

![FCJ_ws2](/images/3.codecommit/11.png)
