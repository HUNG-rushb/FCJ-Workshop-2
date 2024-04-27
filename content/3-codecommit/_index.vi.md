---
title: "AWS CodeCommit"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

![FCJ_ws2](/images/3.codecommit/aws_codecommit.png)

**CodeCommit** là một dịch vụ quản lý mã nguồn hoàn toàn được quản lý, chứa các kho lưu trữ Git an toàn. Nó giúp các nhóm dễ dàng hợp tác trên mã nguồn trong một hệ sinh thái an toàn và có khả năng mở rộng cao. Chọn biểu tượng + bên cạnh mỗi lợi ích để tìm hiểu thêm.

Với CodeCommit, bạn có thể:

- **Hưởng lợi từ dịch vụ được quản lý hoàn toàn do AWS cung cấp**. CodeCommit cung cấp sẵn có sẵn và độ bền cao và loại bỏ các chi phí quản lý phần cứng và phần mềm của riêng bạn. Không có phần cứng cần phải cung cấp và mở rộng và không có phần mềm máy chủ cần cài đặt, cấu hình và cập nhật.
- **Lưu trữ mã nguồn của bạn một cách an toàn**. Kho lưu trữ CodeCommit được mã hóa ở trạng thái nghỉ ngơi cũng như trong quá trình truyền tải.
- **Hợp tác làm việc trên mã nguồn**. Kho lưu trữ CodeCommit hỗ trợ yêu cầu kéo, nơi người dùng có thể xem xét và bình luận về các thay đổi mã nguồn của nhau trước khi hợp nhất chúng vào các nhánh; thông báo tự động gửi email cho người dùng về yêu cầu kéo và bình luận; và nhiều hơn nữa. -** Dễ dàng mở rộng các dự án quản lý phiên bản của bạn**. Kho lưu trữ CodeCommit có thể mở rộng để đáp ứng nhu cầu phát triển của bạn. Dịch vụ có thể xử lý các kho lưu trữ với số lượng lớn tệp hoặc nhánh, kích thước tệp lớn và lịch sử sửa đổi dài.
- **Lưu trữ bất cứ điều gì, bất cứ lúc nào**. CodeCommit không có giới hạn về kích thước của kho lưu trữ của bạn hoặc về các loại tệp bạn có thể lưu trữ.
- **Tích hợp với các dịch vụ AWS và bên thứ ba khác**. CodeCommit giữ cho các kho lưu trữ của bạn gần với các nguồn tài nguyên sản xuất khác của bạn trong Đám mây AWS, giúp tăng tốc độ và tần suất của vòng đời phát triển của bạn. Nó được tích hợp với IAM và có thể được sử dụng với các dịch vụ AWS khác và song song với các kho lưu trữ khác. Để biết thêm thông tin, xem Tích hợp sản phẩm và dịch vụ với AWS CodeCommit.
- **Dễ dàng di chuyển tệp từ các kho lưu trữ từ xa khác**. Bạn có thể di chuyển sang CodeCommit từ bất kỳ kho lưu trữ dựa trên Git nào.
- **Sử dụng các công cụ Git bạn đã biết**. CodeCommit hỗ trợ các lệnh Git cũng như các lệnh và API AWS CLI riêng của mình.
- **Vòng đời phát triển nhanh hơn**. CodeCommit giữ cho các kho lưu trữ của bạn gần với môi trường xây dựng, sân khấu và sản xuất của bạn trong Đám mây AWS. Bạn có thể chuyển các thay đổi tăng dần thay vì toàn bộ ứng dụng. Điều này giúp bạn tăng tốc độ và tần suất của vòng đời phát triển của bạn.

### Nội dung

1.  [Tạo repo CodeCommit](3.1-repo/)
2.  [Push code lên repo](3.2-code/)
