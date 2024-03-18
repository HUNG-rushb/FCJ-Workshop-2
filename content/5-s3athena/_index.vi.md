---
title: "Truy vấn log với AWS Athena"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Sử dụng **Athena** với **CloudTrail** log là một cách để nâng cao khả năng phân tích của bạn về hoạt động dịch vụ AWS. Ví dụ: bạn có thể sử dụng truy vấn để xác định xu hướng và tách biệt hơn nữa hoạt động theo thuộc tính, chẳng hạn như địa chỉ IP nguồn hoặc người dùng.

1. Truy cập vào [CloudTrail console](https://console.aws.amazon.com/cloudtrail/). Ở bảng điều hướng bên trái, chọn **Event history**. Sau đó chọn **Create Athena table**.

![S3](/images/5.athena/51.png)

2. Tại muc **Storage location**, chọn bucket **aws-cloud-trail-logs-workshop** mà ta đang dùng để lưu trữ CloudTrail log. Sau đó chọn **Create table**.

![S3](/images/5.athena/52.png)

3. Xác nhận Athena table **cloudtrail_logs_aws_cloudtrail_logs_workshop** đã được tạo.

![S3](/images/5.athena/53.png)

4. Tìm và chọn service **Athena**, sau đó chọn **Launch query editor**.

![S3](/images/5.athena/53-1.png)
![S3](/images/5.athena/53-2.png)

5. Nếu như đây là lần đầu bạn sử dụng Athena thì ấn **Edit settings**, nếu không thì bạn có thể tiếp tục tại bước số 10.

![S3](/images/5.athena/54.png)

6. Ấn **Browse S3**.

![S3](/images/5.athena/55.png)

7. Chọn 1 bucket để lưu kết quả khi query, ở đây chúng ta sử dụng bucket **logging-workshop-destination**.

![S3](/images/5.athena/56.png)

8. Kiểm tra và ấn **Save**.

![S3](/images/5.athena/57.png)

9. Kiểm tra và ấn **Editor** để quay trở về.

![S3](/images/5.athena/58.png)

10. Copy đoạn code dưới đây vào editor, hãy đảm bảo tên table mà ta đang query giống với tên table ở bảng bên trái. Query này sẽ lọc ra những log hành động **GetObject** có eventsource là **s3.amazonaws.com**. Sau đó ấn **Run**.

```sql
SELECT *
FROM cloudtrail_logs_aws_cloudtrail_logs_workshop
WHERE
    eventsource = 's3.amazonaws.com' AND
    eventname in ('GetObject')
```

![S3](/images/5.athena/59.png)

11. Kiểm tra kết quả query ở ngay bên dưới.

![S3](/images/5.athena/60.png)

12. Sau khi thành công, hãy chạy đoạn query sau trong editor để xóa table

```sql
DROP TABLE `cloudtrail_logs_aws_cloudtrail_logs_workshop`

```

![S3](/images/6.clean/61.png)
