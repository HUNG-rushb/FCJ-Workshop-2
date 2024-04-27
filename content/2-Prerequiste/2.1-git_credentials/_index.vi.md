---
title: "Tạo HTTPS Git Credentials cho CodeCommit"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

Với Git credential, bạn có thể tạo username và static password trong IAM Console mà bạn có thể sử dụng để truy cập **AWS CodeCommit** từ cmd, Git CLI hoặc bất kỳ công cụ Git nào hỗ trợ xác thực HTTPS.

Vì đây là static credentials nên chúng có thể được cached bằng cách sử dụng các công cụ quản lý mật khẩu có trong hệ điều hành local của bạn hoặc được lưu trữ trong tiện ích quản lý thông tin xác thực. Điều này cho phép bạn bắt đầu với AWS CodeCommit trong vòng vài phút. Bạn không cần tải xuống AWS CLI hoặc đặt cấu hình ứng dụng khách Git để kết nối với kho lưu trữ **CodeCommit** trên HTTPS. Bạn cũng có thể sử dụng username và password để kết nối với **CodeCommit** từ các công cụ của bên thứ ba hỗ trợ xác thực tên username và password, bao gồm các ứng dụng khách GUI Git phổ biến (như TowerUI) và IDE (như Eclipse, IntelliJ và Visual Studio).

### Tạo HTTPS Git Credentials cho CodeCommit

1. Từ root account, truy cập vào IAM console của IAM account mà bạn sẽ sử dụng cho bài lab này, chọn mục **Security credentials**.

![FCJ_ws2](/images/2.prerequisite/_1.png)

2. Ở phần **HTTPS Git credentials for AWS CodeCommit**, chọn **Generate credentials**

![FCJ_ws2](/images/2.prerequisite/_2.png)

3. Chọn **Download credentials**, và lưu nó ở nơi bạn có thể dễ dàng truy cập lại.

![FCJ_ws2](/images/2.prerequisite/_3.png)
