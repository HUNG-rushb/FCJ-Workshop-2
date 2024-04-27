---
title: "Tạo Application load balancer"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.5 </b> "
---

### Tạo Application load balancer

1. Chuyển hướng tới **Load balancers**, chọn **Create load balancer**.

![FCJ_ws2](/images/2.prerequisite/12.png)

2. Chọn **Application Load Balancer**

![FCJ_ws2](/images/2.prerequisite/13.png)

3. \_

- Mục **Load balancer name**, nhập **`FCJ-ALB`**.
- Mục **Scheme**, chọn **Internet-facing** (mặc định).
- Mục **IP address type**, chọn **IPv4** (mặc định).

![FCJ_ws2](/images/2.prerequisite/14.png)

4. Tại mục **Network mapping**:

- Mục **VPC**, chọn **Default VPC**.
- Mục **Mappings**, tick chọn cả 3 **AZ**, sau đó chọn các **fcj-subnet** tương ứng với từng **AZ** mà ta đã tạo.

![FCJ_ws2](/images/2.prerequisite/15.png)

5. Tại mục **Security groups**, mở bảng dropdown, bỏ chọn **default** và chọn **FCJ-SG**.

![FCJ_ws2](/images/2.prerequisite/16.png)

![FCJ_ws2](/images/2.prerequisite/17.png)

6.  Tại mục **Listeners and routing**, tại **Default action**, chọn target group **FCJ-TG**.

![FCJ_ws2](/images/2.prerequisite/18.png)

7. Kiểm tra lại cấu hình.

![FCJ_ws2](/images/2.prerequisite/19.png)

8. Xác nhận ALB đã được tạo thành công.

![FCJ_ws2](/images/2.prerequisite/20.png)
