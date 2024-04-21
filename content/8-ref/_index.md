---
title: "Reference"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

We will take the following steps to delete the resources we created in this exercise.

### Xóa Athena query

1. Find and select service **Athena**, then select **Launch query editor**, select tab **Settings**, click **Manage**.

2. Click _X_ to delete the connections to bucket, click **Save**.

### Xóa CloudTrail

3. Find and select service **CloudTrail**, select **Trails** on left panel. Select trail **S3_logging_workshop**, then select **Delete**.

4. Confirm **Delete**.

### Xóa S3 buckets

5. Find and select service **S3**, select bucket **logging_workshop**. We have to empty the bucket before delete it. Select all files then click **Delete**.

6. Confirmto delete. click **Delete objects**.

7. Return to buckets list, then select bucket **logging_workshop**, select **Delete**.

8. Confirm bucket's name and click **Delete bucket**.

9. Repeat delete step from step 5 to delete 2 remainings buckets, **logging-workshop-destinations** và **aws-cloudtrail-log-workshop**.
