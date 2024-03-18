---
title: "Logging with AWS CloudTrail"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

- CloudTrail includes 3 main components:
  - **Event** A record of an activity in an AWS account..
  - **Trail** A trail enables CloudTrail to deliver log files to an Amazon S3 bucket, CloudWatch logs, and CloudWatch events.
  - **Log bucket** The target S3 bucket where logs files are delivered.

### Kích hoạt Server access logging

1. In **AWS Console**, find and choose **Cloudtrail**.

![S3](/images/4.s3cloudtrail/41.png)

2. Select **Create trail**

![S3](/images/4.s3cloudtrail/42.png)

3. Continue:

- For **Trail name**, insert **`S3_logging_workshop`**.
- For **Trail log bucket and folder**, insert **`aws-cloud-trail-logs-workshop`**.
- For **Log file SSE-KMS encryption**, untick **Enable**.

![S3](/images/4.s3cloudtrail/43.png)

4. Scroll down and select **Next**.

![S3](/images/4.s3cloudtrail/44.png)

5. For **Event type**, tick **Data events**.

![S3](/images/4.s3cloudtrail/45.png)

6. Scroll down, for **Data events**, select **S3**. Then hit **Next**.

![S3](/images/4.s3cloudtrail/46.png)

7. Review and select **Create trail**.

![S3](/images/4.s3cloudtrail/47.png)

8. Confirm trail is created.

![S3](/images/4.s3cloudtrail/48.png)

9. Return **S3 console**, we can see that **aws-cloud-trail-logs-workshop** is created for storing logs.

![S3](/images/4.s3cloudtrail/49.png)

10. Open private tab and access the file.

11. Wait 10 minuts then refresh. Follow, get into inners folder until you can see the logs.

![S3](/images/4.s3cloudtrail/59.png)

12. Select a file and **Download**.

![S3](/images/4.s3cloudtrail/60.png)

12. Log file will look like this:

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
