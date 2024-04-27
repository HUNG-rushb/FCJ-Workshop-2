---
title: "Cập nhật và quan sát deployment"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6.6 </b> "
---

### Cập nhật và quan sát deployment

1. Trở về source code, mở file **`src/components/Calculator.js`**. Thay đổi **dòng 137** từ **Version 1.0** sang **2.0**.

![FCJ_ws2](/images/6.codedeploy/33_1.png)

2. Thực hiện đẩy code lên repo:

- Chạy **`git add .`**.
- Chạy **`git commit -m "Update to 2.0"`** để commit code trên local.
- Chạy **`git push origin master`** để đẩy code lên repo trên **CodeCommit**.

![FCJ_ws2](/images/6.codedeploy/33_2.png)

3. Trở về pipeline console, quan sát pipeline sẽ được trigger và chạy source **Update to 2.0**, và stage **Deploy** được chạy thành công.

![FCJ_ws2](/images/6.codedeploy/34.png)

4. Trở về **ECS** console, vào xem tasks của cluster **FCJ_Cluser**, chúng ta sẽ thấy 3 task mới **Running**, đây chính là **Green enviroment**, trong khi đó 3 task cũ là **Blue enviroment**.

![FCJ_ws2](/images/6.codedeploy/34_1.png)

5. Truy cập **CodeDeploy**, chọn **Deployments** từ menu bên trái, chúng ta sẽ thấy deployment của application đang **In progress...**. Nhấn vào để xem chi tiết.

![FCJ_ws2](/images/6.codedeploy/35.png)

6. Hình bên dưới đang cho thấy traffic gửi đến **DNS name của FCJ_ALB** đang được chuyển từ **Blue enviroment (90%)** sang **Green enviroment (10%)**, đồng nghĩa với việc chuyển từ ứng dụng **Version 1.0** sang **2.0**.

- Chúng ta đã cấu hình cho việc này là **10% mỗi phút (bước 5 phần 6.4)**.

![FCJ_ws2](/images/6.codedeploy/36.png)

7. Hãy mở một tab khác, hoặc một trình duyệt khác.

- Truy cập **DNS name của FCJ_ALB (bước 17 phần 6.4)**.
- Hãy thử **hard refresh (Ctrl + R)** vài lần.
- Bạn sẽ thấy có lúc bạn nhận được **Version 1.0**, có lúc là **Version 2.0**.
- Thử nghiệm sẽ rõ ràng hơn khi có càng nhiều % traffic được chuyển từ **Blue enviroment** sang **Green enviroment**.

![FCJ_ws2](/images/6.codedeploy/37.png)

8. 6 task, 3 task cho mỗi bên **Blue và Green**, sẽ cùng nhau tồn tại song song cho tới khi quá trình deploy thành công.

- Bạn có thể phân biệt cũ và mới bằng cách xem **version của task definition**. Như trong hình thì mới là **10** và cũ là **9**.

![FCJ_ws2](/images/6.codedeploy/38_1.png)

9. Hình này thể hiện việc tất cả traffic đã được chuyển từ **Blue enviroment (0%)** sang **Green enviroment (100%)**. Từ đây, **Blue enviroment hiện tại** sẽ được terminate, **Green enviroment hiện tại** sẽ lên làm **Blue enviroment mới**.

- Step 3 của deployment sẽ **đợi 15 phút (bước 13 phần 6.4)** để chắc chắn hệ thống ổn định, nếu có gì gây ra deploy hỏng, hệ thống sẽ tự động roll back. Còn không, nếu mọi thứ ổn định thì **Green enviroment hiện tại** sẽ được terminate.

![FCJ_ws2](/images/6.codedeploy/38.png)

10. 3 task của **Blue enviroment cũ (task definition 9)** đã được terminate và 3 task mới **(task definition 10)** sẽ lên làm **Blue enviroment mới**, phục vụ **100%** traffic từ người dùng.

![FCJ_ws2](/images/6.codedeploy/39_1.png)

11. Tất cả các step của deployment đã được thực hiện thành công.

![FCJ_ws2](/images/6.codedeploy/39.png)

12. Xác nhận pipeline đã chạy source **Update to 2.0** thành công.

![FCJ_ws2](/images/6.codedeploy/40.png)

### Vậy là bạn đã hoàn thành một **Blue/Green deployment pipeline** sử dụng **AWS CodePipeline**.
