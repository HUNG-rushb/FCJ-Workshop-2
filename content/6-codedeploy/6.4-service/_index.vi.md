---
title: "Tạo Cluster service"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 6.4 </b> "
---

### Tạo Cluster service

1. Truy cập tới **AWS ECS**, vào danh sách **Clusters**, và chọn cluster **FCJ_Cluster**.

![FCJ_ws2](/images/6.codedeploy/10.png)

2. Chọn **Create** trong tab **Services**.

![FCJ_ws2](/images/6.codedeploy/11.png)

3. Mục **Compute options**, chọn **Launch type**, và chọn **Fargate** (mặc định), **Platform version** là **LATEST**.

![FCJ_ws2](/images/6.codedeploy/12.png)

4. Tại **Deployment configuration**:

- Mục **Application type**, chọn **Service**.
- Mục **Family**, chọn **FCJ_Task_Definition**, **Revision** tự động chọn bản **LATEST**.
- Mục **Project name**, chọn **FCJ_Build_Project**.
- Mục **Service name**, nhập **`FCJ_Service`**.
- Mục **Desired tasks**, nhập **`3`**.

![FCJ_ws2](/images/6.codedeploy/13.png)

5. Tiếp tục:

- Mục **Deployment options**, chọn **Blue/green deployment (powered by AWS CodeDeploy)**.
- Mục **Deployment configuration**, chọn **CodeDeployDefault.ECSLinear10PercentEvery1Minutes**.
- Mục **Service role for CodeDeploy**, chọn **CodeDeployServiceRole**.

![FCJ_ws2](/images/6.codedeploy/14.png)

6.  Tại **Networking**:

- Mục **VPC**, chọn **Default VPC**.
- Mục **Subnets**, chọn 3 puclic subnet **fcj-subnet-...**.
- Mục **Security group**, chọn **Use an existing security group**, sau đó chọn thêm **FCJ_SG**, sẽ có 2 security group như trong hình.
- Mục **Public IP**, chọn **Turned on**.

![FCJ_ws2](/images/6.codedeploy/15.png)

7.  Tại **Load balancing**:

- Mục **Load balancer type**, chọn **Application Load Balancer**.
- Mục **Application Load Balancer**, chọn **Use an existing load balancer**.
- Mục **Load balancer**, chọn **FCJ_ALB**.
- Mục **Health check grace periodInfo**, nhập **`0`**.

![FCJ_ws2](/images/6.codedeploy/16.png)

8.  Tiếp tục:

- Mục **Listeners**, mục **Production listener**, chọn **Use an existing listener** và chọn **80:HTTP**.
- Kiểm tra target group là **FCJ_TG**.

![FCJ_ws2](/images/6.codedeploy/17.png)

9.  Tại **Target groups**:

- Mục **Application type**, chọn **Service**.
- Mục **Target group 1**, chọn **Use an existing target group** và sau đó chọn **FCJ_TG** ở dropdown bên phải.
- Mục **Target group 2**, chọn **Create new target group**.
- Mục **Target group 2 name**, nhập **`FCJ-TG-Blue`**.
- Sau đó kéo xuống dưới cùng và chọn **Create** (không có trong hình).

![FCJ_ws2](/images/6.codedeploy/18.png)

10. Truy cập tới dịch vụ **AWS CloudFormation**, chúng ta sẽ thấy có 1 stack mới đang được khởi tạo, đây chính là stack chứa service của chúng ta.

![FCJ_ws2](/images/6.codedeploy/19.png)

11. Sau khi stack tạo thành công, truy cập tới dịch vụ **AWS CodeDeploy**, vào **Applications**, chúng ta sẽ thấy một application có dạng **AppECS-...**. Đây là application mà **ECS** sử dụng để deploy ứng dụng. Nhấn vào application để quan sát.

![FCJ_ws2](/images/6.codedeploy/19_1.png)

12. Chọn tab **Deployment groups**, chọn deployment group duy nhất trong đó, và chọn **Edit**.

![FCJ_ws2](/images/6.codedeploy/19_2.png)

13. Kéo xuống bên dưới, tại phần **Deployment settings**, chình thời gian **Original revision termination** thành **0 hour 15 minutes** như trong hình. Nhấn **Save changes**.

![FCJ_ws2](/images/6.codedeploy/19_3.png)

14. Quay về **ECS** console, kiểm tra **Services** của cluster thì ta sẽ thấy **FCJ_Service** đang chạy thành công.

![FCJ_ws2](/images/6.codedeploy/20.png)

15. Chuyển sang tab **Tasks**, chúng ta sẽ thấy có 3 task đang **Running**.

![FCJ_ws2](/images/6.codedeploy/21.png)

16. Truy cập tới dịch vụ **AWS EC2**, tới **Load balancers**, chọn **FCJ_ALB** và copy **DNS Name**.

![FCJ_ws2](/images/6.codedeploy/22.png)

17. Truy cập địa chỉ DNS của ALB, chúng ta sẽ được điều hướng tới các **Fargate container** đang host ứng dụng Calculator. **Hãy chú ý bạn sẽ phải kết nối bằng HTTP**.

![FCJ_ws2](/images/6.codedeploy/23.png)
