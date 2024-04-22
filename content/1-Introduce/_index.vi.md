---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

![FCJ_ws2](/images/1.introduce/aws.png)

**Blue/Green Deployment** là một quy trình triển khai liên tục nhằm giảm thời gian chết và rủi ro bằng cách có hai môi trường production giống hệt nhau, được gọi là Blue và Green.

Giả sử môi trường **Blue** đang hoạt động và môi trường **Green** là phiên bản mới của ứng dụng bạn sẽ triển khai. Khi developer muốn publish những thay đổi mới về code nào - bản phát hành tính năng mới, phiên bản mới của ứng dụng, v.v. - công việc trên phiên bản mới được thực hiện trong môi trường **Green**, trong khi phiên bản cũ được duy trì trong Blue. Khi quá trình phát hành mới kết thúc, bộ cân bằng tải sẽ chuyển tất cả lưu lượng sản xuất sang phiên bản **Green** và trở thành **Blue** mới, trong khi đó phiên bản **Blue cũ** sẽ được duy trì như một bản sao lưu hoặc bị terminate.

![FCJ_ws2](/images/1.introduce/bg.jpg)

Ưu điểm của chiến lược **Blue/Green Deployment** là :

- **Testing parity**: tính năng này có nghĩa là các thử nghiệm phản ánh thực sự thực tế của sản xuất.
- **Triển khai bất kỳ lúc nào**: không có downtime có nghĩa là chúng ta có thể phát hành bất kỳ lúc nào. Không cần phải đợi các maintenance windows.
- **Chuyển tiếp tức thì**: người dùng được chuyển sang phiên bản mới ngay lập tức, hoặc gần như vậy. Mọi người đều xem bản phát hành mới nhất cùng một lúc.
- **Khôi phục tức thì**: phần chuyển tiếp hoạt động theo cả hai cách. Nếu chúng ta quyết định quay lại phiên bản trước, chúng ta có thể chuyển tất cả người dùng trở lại ngay lập tức.
- **Hot standby**: Blue-Green có thể cứu chúng ta khỏi các tình huống thảm họa. Giả sử rằng một trung tâm dữ liệu chuyển sang chế độ ngoại tuyến, chúng ta sẽ chuyển sang cái khác cho đến khi sự cố được khắc phục. Điều này sẽ hoạt động miễn là chúng ta đã có biện pháp phòng ngừa là không đặt Blue-Green vào cùng một vùng khả dụng.
- **Postmortem**: việc gỡ lỗi các bản phát hành không thành công rất khó khăn với việc triển khai tại chỗ. Khi đối mặt với downtime, ưu tiên luôn là trở lại trạng thái bình thường. Việc thu thập dữ liệu gỡ lỗi chỉ là thứ yếu, vì vậy nhiều thông tin có giá trị có thể bị mất trong quá trình khôi phục. Blue-green không gặp phải vấn đề này — Các lần khôi phục luôn giữ nguyên việc triển khai thất bại để phân tích.

Song song với đó thì chiến lược này cũng có một vài nhược điểm, có thể kể đến:

- **Tiêu tốn nhiều tài nguyên** do cần duy trì 2 môi trường cùng lúc khi triển khai
- **Blue/Green Deployment** đòi hỏi các service trên cả 2 môi trường sử dụng chung database, trong trường hợp code mới có tác động thay đổi cấu trúc database, cần xây dựng chiến lược đồng bộ sao cho cả hai môi trường có thể chạy cùng lúc mà không gặp sự cố. Với vấn đề này, ta có thể sử dụng liquibase để xây dựng giải pháp.

Với **AWS**, bạn có thể deploy **Blue/Green deployments** sử dụng **Amazon ECS**, **Application Load Balancer** và **target groups**.

{{% notice note %}}
A notice disclaimer
{{% /notice %}}
