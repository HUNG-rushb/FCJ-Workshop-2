---
title: "Bật S3 Server Access Logging"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3. </b> "
---

Server access logging cung cấp cho bạn khả năng hiển thị các hoạt động cấp đối tượng chi tiết trên dữ liệu của bạn. Log là tệp văn bản có một dòng cho mỗi bản ghi nhật ký. Mỗi log đại diện cho một yêu cầu và bao gồm các trường được phân cách bằng dấu cách.

Các trường liên quan đến operation, requester, resource và thông tin session. Dưới đây là một ví dụ:

```
79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be awsexamplebucket1 [06/Feb/2019:00:00:38 +0000] 192.0.2.3 79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be 3E57427F3EXAMPLE REST.GET.VERSIONING - "GET /awsexamplebucket1?versioning HTTP/1.1" 200 - 113 - 7 - "-" "S3Console/0.4" - s9lzHYrFp76ZVxRcpX9+5cjAnEH2ROuNkd2BHfIa6UkFVdtjf5mKR3/eTPFvsiP/XV/VLi31234= SigV2 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader awsexamplebucket1.s3.us-west-1.amazonaws.com TLSV1.1
```

### Kích hoạt Server access logging

1. Trong giao diện S3, chọn bucket **logging-workshop**.

![S3console](/images/3.connect/30.png)

2. Trong giao diện bucket, chọn **Properties**.

![CreateBucket](/images/3.connect/31.png)

3. Kéo xuống tại muc **Server access logging**, chọn **Edit**

![CreateBucket](/images/3.connect/32.png)

4. Chọn **Enable**, sau đó chọn **Brow S3** để chọn bucket lưu log.

![CreateBucket](/images/3.connect/33.png)

5. Chọn bucket **logging-workshop-destination**, sau đó nhấn **Choose destination**.

![CreateBucket](/images/3.connect/34.png)

6. Review lại bucket lưu log, sau đó nhấn **Save changes**.

![CreateBucket](/images/3.connect/35.png)

7. Xác nhận **Server access logging** đã được bật.

![CreateBucket](/images/3.connect/36.png)
