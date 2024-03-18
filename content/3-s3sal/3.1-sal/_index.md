---
title: "Enable S3 Server access logging"
date: "`r Sys.Date()`"
weight: 1
chapter: true
pre: " <b> 3.1 </b> "
---

In this step, we will enable **Server access logging**.

Server access logs give you visibility into detailed object-level operations on your data. The log files are text files that have one line for each log record. Each log record represents one request and consists of space-delimited fields.

The fields relate to operation, requester, resource, and session information. Here is an example:

```
79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be awsexamplebucket1 [06/Feb/2019:00:00:38 +0000] 192.0.2.3 79a59df900b949e55d96a1e698fbacedfd6e09d98eacf8f8d5218e7cd47ef2be 3E57427F3EXAMPLE REST.GET.VERSIONING - "GET /awsexamplebucket1?versioning HTTP/1.1" 200 - 113 - 7 - "-" "S3Console/0.4" - s9lzHYrFp76ZVxRcpX9+5cjAnEH2ROuNkd2BHfIa6UkFVdtjf5mKR3/eTPFvsiP/XV/VLi31234= SigV2 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader awsexamplebucket1.s3.us-west-1.amazonaws.com TLSV1.1
```

### Kích hoạt Server access logging

1. In S3 console, select bucket **logging-workshop**.

![S3console](/images/3.connect/30.png)

2. In bucket console, select **Properties**.

![CreateBucket](/images/3.connect/31.png)

3. Scroll dowm to **Server access logging**, select **Edit**

![CreateBucket](/images/3.connect/32.png)

4. Select **Enable**, then select **Brow S3** for storing the logs afterward.

![CreateBucket](/images/3.connect/33.png)

5. Select bucket **logging-workshop-destination**, then select **Choose destination**.

![CreateBucket](/images/3.connect/34.png)

6. Review bucket, then select **Save changes**.

![CreateBucket](/images/3.connect/35.png)

7. Confirm **Server access logging** is enabled.

![CreateBucket](/images/3.connect/36.png)
