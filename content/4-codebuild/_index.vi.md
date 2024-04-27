---
title: "AWS CodeBuild"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/aws_codebuild.png)

**AWS CodeBuild** là một dịch vụ xây dựng quản lý hoàn toàn trong đám mây. **CodeBuild** biên dịch mã nguồn của bạn, chạy các bài kiểm tra đơn vị và tạo ra các tài liệu sẵn sàng triển khai. **CodeBuild** loại bỏ nhu cầu cung cấp, quản lý và mở rộng máy chủ xây dựng của riêng bạn. Nó cung cấp môi trường xây dựng được đóng gói trước cho các ngôn ngữ lập trình phổ biến và các công cụ xây dựng như **Apache Maven**, **Gradle**, và nhiều hơn nữa. Bạn cũng có thể tùy chỉnh môi trường xây dựng trong **CodeBuild** để sử dụng các công cụ xây dựng của riêng bạn. **CodeBuild** tự động mở rộng để đáp ứng các yêu cầu xây dựng cao nhất.

**CodeBuild** cung cấp những lợi ích sau:

- **Quản lý hoàn toàn** – **CodeBuild** loại bỏ nhu cầu cài đặt, vá lỗi, cập nhật và quản lý máy chủ xây dựng của riêng bạn.
- **Theo yêu cầu** – **CodeBuild** tự động mở rộng để đáp ứng nhu cầu xây dựng của bạn. Bạn chỉ trả tiền cho số phút xây dựng bạn tiêu thụ.
- **Sẵn sàng sử dụng** – **CodeBuild** cung cấp môi trường xây dựng được cấu hình trước cho các ngôn ngữ lập trình phổ biến nhất. Bạn chỉ cần trỏ đến tập lệnh xây dựng của mình để bắt đầu xây dựng đầu tiên của bạn.
- **Hỗ trợ liên tục tích hợp và triển khai** - **CodeBuild** thuộc một họ công cụ phát triển AWS, mà bạn có thể sử dụng để tạo các luồng công việc phát hành phần mềm tự động hoàn chỉnh cho tích hợp liên tục và triển khai (CI/CD). Bạn cũng có thể tích hợp **CodeBuild** vào luồng công việc CI/CD hiện tại của mình. Ví dụ, bạn có thể sử dụng **CodeBuild** như một nút công nhân cho cài đặt máy chủ Jenkins hiện tại của mình để xây dựng phân tán.
- **Bảo mật** - Với **CodeBuild**, các tài liệu xây dựng của bạn được mã hóa bằng các khóa cụ thể cho khách hàng được quản lý bởi **Dịch vụ Quản lý Khóa AWS (AWS KMS)**. **CodeBuild** được tích hợp với **IAM**, vì vậy bạn có thể gán quyền cụ thể cho dự án xây dựng của mình

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/aws_ecr.png)

**Amazon Elastic Container Registry (Amazon ECR)** là một dịch vụ lưu trữ hình ảnh container được quản lý bởi AWS, an toàn, có khả năng mở rộng và đáng tin cậy. **Amazon ECR** hỗ trợ các kho lưu trữ riêng với quyền dựa trên tài nguyên sử dụng **AWS IAM**. Điều này là để người dùng hoặc các máy **Amazon EC2** cụ thể có thể truy cập vào các kho lưu trữ và hình ảnh container của bạn. Bạn có thể sử dụng CLI ưa thích của mình để đẩy, kéo và quản lý hình ảnh Docker, hình ảnh Open Container Initiative (OCI) và các tác phẩm tương thích OCI.

**Amazon ECR** cung cấp các tính năng sau:

- Chính sách vòng đời giúp quản lý vòng đời của các hình ảnh trong các kho lưu trữ của bạn. Bạn xác định các quy tắc dẫn đến việc dọn dẹp các hình ảnh không sử dụng. Bạn có thể thử nghiệm các quy tắc trước khi áp dụng chúng vào kho lưu trữ của bạn. Để biết thêm thông tin, xem Chính sách vòng đời.

- Quét hình ảnh giúp xác định các lỗ hổng phần mềm trong các hình ảnh container của bạn. Mỗi kho lưu trữ có thể được cấu hình để quét khi đẩy. Điều này đảm bảo rằng mỗi hình ảnh mới đẩy vào kho lưu trữ được quét. Bạn sau đó có thể lấy kết quả của quét hình ảnh. Để biết thêm thông tin, xem Quét hình ảnh.

- Sao chép giữa các vùng và tài khoản giúp bạn dễ dàng có hình ảnh ở nơi bạn cần chúng. Điều này được cấu hình như một cài đặt kho lưu trữ và trên cơ sở từng vùng. Để biết thêm thông tin, xem Cài đặt kho lưu trữ riêng tư.

- Quy tắc bộ nhớ cache cung cấp một cách để bộ nhớ cache các kho lưu trữ trong một kho lưu trữ trên cấp cao hơn trong kho lưu trữ riêng tư Amazon ECR của bạn. Sử dụng quy tắc bộ nhớ cache, Amazon ECR sẽ định kỳ liên hệ với kho lưu trữ trên cấp cao hơn để đảm bảo rằng hình ảnh được bộ nhớ cache trong kho lưu trữ riêng tư Amazon ECR của bạn là mới nhất. Để biết thêm thông tin, xem Sử dụng quy tắc bộ nhớ cache.

### Nội dung

1.  [Tạo private repo ECR](4.1-ecr_repo/)
2.  [Tạo CodeBuild project](4.2-build_project/)
3.  [Cập nhật quyền cho codebuild role](4.3-role/)
