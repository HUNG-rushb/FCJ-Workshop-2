---
title: "Clean up"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

We will take the following steps to delete the resources we created in this exercise.

### Xóa Athena query

1. Find and select service **Athena**, then select **Launch query editor**, select tab **Settings**, click **Manage**.

![S3](/images/6.clean/62.png)

2. Click _X_ to delete the connections to bucket, click **Save**.

![S3](/images/6.clean/63.png)

### Xóa CloudTrail

3. Find and select service **CloudTrail**, select **Trails** on left panel. Select trail **S3_logging_workshop**, then select **Delete**.

![S3](/images/6.clean/90.png)

4. Confirm **Delete**.

![S3](/images/6.clean/91.png)

### Xóa S3 buckets

5. Find and select service **S3**, select bucket **logging_workshop**. We have to empty the bucket before delete it. Select all files then click **Delete**.

![S3](/images/6.clean/64.png)

6. Confirmto delete. click **Delete objects**.

![S3](/images/6.clean/65.png)

7. Return to buckets list, then select bucket **logging_workshop**, select **Delete**.

![S3](/images/6.clean/66.png)

8. Confirm bucket's name and click **Delete bucket**.

![S3](/images/6.clean/67.png)

9. Repeat delete step from step 5 to delete 2 remainings buckets, **logging-workshop-destinations** và **aws-cloudtrail-log-workshop**.
