---
title: "Truy vấn log với AWS Athena"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Sử dụng **Athena** với **CloudTrail** log là một cách để nâng cao khả năng phân tích của bạn về hoạt động dịch vụ AWS. Ví dụ: bạn có thể sử dụng truy vấn để xác định xu hướng và tách biệt hơn nữa hoạt động theo thuộc tính, chẳng hạn như địa chỉ IP nguồn hoặc người dùng.

1. Truy cập vào [CloudTrail console](https://console.aws.amazon.com/cloudtrail/). Ở bảng điều hướng bên trái, chọn **Event history**. Sau đó chọn **Create Athena table**.

2. Tại muc **Storage location**, chọn bucket **aws-cloud-trail-logs-workshop** mà ta đang dùng để lưu trữ CloudTrail log. Sau đó chọn **Create table**.

3. Xác nhận Athena table **cloudtrail_logs_aws_cloudtrail_logs_workshop** đã được tạo.

4. Tìm và chọn service **Athena**, sau đó chọn **Launch query editor**.

5. Nếu như đây là lần đầu bạn sử dụng Athena thì ấn **Edit settings**, nếu không thì bạn có thể tiếp tục tại bước số 10.

6. Ấn **Browse S3**.

7. Chọn 1 bucket để lưu kết quả khi query, ở đây chúng ta sử dụng bucket **logging-workshop-destination**.

8. Kiểm tra và ấn **Save**.

9. Kiểm tra và ấn **Editor** để quay trở về.

10. Copy đoạn code dưới đây vào editor, hãy đảm bảo tên table mà ta đang query giống với tên table ở bảng bên trái. Query này sẽ lọc ra những log hành động **GetObject** có eventsource là **s3.amazonaws.com**. Sau đó ấn **Run**.

```sql
SELECT *
FROM cloudtrail_logs_aws_cloudtrail_logs_workshop
WHERE
    eventsource = 's3.amazonaws.com' AND
    eventname in ('GetObject')
```

11. Kiểm tra kết quả query ở ngay bên dưới.

12. Sau khi thành công, hãy chạy đoạn query sau trong editor để xóa table

```sql
DROP TABLE `cloudtrail_logs_aws_cloudtrail_logs_workshop`

```
