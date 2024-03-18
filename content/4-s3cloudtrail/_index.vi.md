---
title: "Logging với AWS CloudTrail"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

- Cách hoạt động của CloudTrail bao gồm 3 thành phần chính:
  - **Event** là record về một hoạt động trong tài khoản AWS.
  - **Trail** cho phép CloudTrail phân phối log tới bucket Amazon S3, CloudWatch log và CloudWatch event.
  - **Log bucket** dùng để lưu trữ các file log.

### Kích hoạt Server access logging

1. Trong giao diện **AWS Console**, tìm và chọn **Cloudtrail**.

![S3](/images/4.s3cloudtrail/41.png)

2. Chọn **Create trail**

![S3](/images/4.s3cloudtrail/42.png)

3. Thực hiện:

- Mục **Trail name**, nhập **`S3_logging_workshop`**.
- Mục **Trail log bucket and folder**, nhập **`aws-cloud-trail-logs-workshop`**.
- Mục **Log file SSE-KMS encryption**, bỏ tick **Enable**.

![S3](/images/4.s3cloudtrail/43.png)

4. Kéo xuống dưới và chọn **Next**.

![S3](/images/4.s3cloudtrail/44.png)

5. Tại mục **Event type**, tick chọn thêm **Data events**.

![S3](/images/4.s3cloudtrail/45.png)

6. Kéo xuống dưới, tại mục **Data events**, chọn **S3**. Sau đó nhấn **Next**.

![S3](/images/4.s3cloudtrail/46.png)

7. Review lại và ấn **Create trail**.

![S3](/images/4.s3cloudtrail/47.png)

8. Kiểm tra trail đã được tạo thành công.

![S3](/images/4.s3cloudtrail/48.png)

9. Quay trở về giao diện **S3 console**, chúng ta có thể thấy bucket **aws-cloud-trail-logs-workshop** đã được tạo ra để lưu log.

![S3](/images/4.s3cloudtrail/49.png)

10. Mở một tab ẩn danh mới và nhập URL truy cập tới file chúng ta đã lưu.

11. Chờ khoảng 10 phút, sau đó refresh. Truy cập vào các folder bên trong cho tới khi chúng ta có thể thấy các file log đã được tạo ra.

![S3](/images/4.s3cloudtrail/59.png)

12. Chọn vào 1 file log bất kỳ, ấn **Download**.

![S3](/images/4.s3cloudtrail/60.png)

12. Khi xem file log đã được tải về, ta có thể thấy nội dung có dạng JSON như sau:

```json
{
  "Records": [
    {
      "eventVersion": "1.09",
      "userIdentity": {
        "type": "IAMUser",
        "principalId": "******",
        "arn": "arn:aws:iam::****:user/****",
        "accountId": "*****",
        "accessKeyId": "*****",
        "userName": "****",
        "sessionContext": {
          "attributes": {
            "creationDate": "2024-03-03T05:32:58Z",
            "mfaAuthenticated": "false"
          }
        }
      },
      "eventTime": "2024-03-03T14:00:32Z",
      "eventSource": "s3.amazonaws.com",
      "eventName": "GetObject",
      "awsRegion": "ap-southeast-1",
      "sourceIPAddress": "118.69.159.186",
      "userAgent": "[Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36 Edg/122.0.0.0]",
      "requestParameters": {
        "X-Amz-Date": "20240303T140026Z",
        "bucketName": "aws-cloudtrail-logs-workshop",
        "X-Amz-Algorithm": "AWS4-HMAC-SHA256",
        "response-content-disposition": "attachment",
        "X-Amz-SignedHeaders": "host",
        "Host": "aws-cloudtrail-logs-workshop.s3.ap-southeast-1.amazonaws.com",
        "X-Amz-Expires": "300",
        "key": "AWSLogs/*****/CloudTrail/ap-southeast-1/2024/03/03/*****_CloudTrail_ap-southeast-1_20240303T1355Z_FXZWnsQMI7Esmlr6.json.gz"
      },
      "responseElements": null,
      "additionalEventData": {
        "SignatureVersion": "SigV4",
        "CipherSuite": "ECDHE-RSA-AES128-GCM-SHA256",
        "bytesTransferredIn": 0,
        "AuthenticationMethod": "QueryString",
        "x-amz-id-2": "0nSxx7oCCBTlrpXwQsLYoA0MqHo/+k/FiMnikrVCDKiWDr1Aoeg7oSqlJvBsYm2J3BnFpU31IUA=",
        "bytesTransferredOut": 7759
      },
      "requestID": "MB8NVKR3FVMSSRM9",
      "eventID": "3d4906c8-52ce-456f-bc0a-a89f07b364a0",
      "readOnly": true,
      "resources": [
        {
          "type": "AWS::S3::Object",
          "ARN": "arn:aws:s3:::aws-cloudtrail-logs-workshop/AWSLogs/*****/CloudTrail/ap-southeast-1/2024/03/03/*****_CloudTrail_ap-southeast-1_20240303T1355Z_FXZWnsQMI7Esmlr6.json.gz"
        },
        {
          "accountId": "*****",
          "type": "AWS::S3::Bucket",
          "ARN": "arn:aws:s3:::aws-cloudtrail-logs-workshop"
        }
      ],
      "eventType": "AwsApiCall",
      "managementEvent": false,
      "recipientAccountId": "*****",
      "eventCategory": "Data",
      "tlsDetails": {
        "tlsVersion": "TLSv1.2",
        "cipherSuite": "ECDHE-RSA-AES128-GCM-SHA256",
        "clientProvidedHostHeader": "aws-cloudtrail-logs-workshop.s3.ap-southeast-1.amazonaws.com"
      }
    }
  ]
}
```
