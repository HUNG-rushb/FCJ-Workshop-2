---
title: "Query logs with Athena"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

Using **Athena** with **CloudTrail** logs is even easier than server access logs. With server access logs, you had to go to the Athena console to create a database and table, but with **CloudTrail** logging, **Athena** will automatically create a table for you.

To use **Athena** with **CloudTrail** logs, simply go to the **CloudTrail** event history and select Run advanced queries in Amazon Athena.

1. Go to [CloudTrail console](https://console.aws.amazon.com/cloudtrail/). On left panel, select **Event history**, select **Create Athena table**.

![S3](/images/5.athena/51.png)

2. for **Storage location**, select bucket **aws-cloud-trail-logs-workshop** which we are using to store logs then select **Create table**.

![S3](/images/5.athena/52.png)

3. Confirm Athena table **cloudtrail_logs_aws_cloudtrail_logs_workshop** created.

![S3](/images/5.athena/53.png)

4. Find select service **Athena**, then select **Launch query editor**.

![S3](/images/5.athena/53-1.png)
![S3](/images/5.athena/53-2.png)

5. If this is the first time you use Athena, select **Edit settings**, if not, skip to step 10.

![S3](/images/5.athena/54.png)

6. Click **Browse S3**.

![S3](/images/5.athena/55.png)

7. Select 1 bucket to store query's result, here we choose bucket **logging-workshop-destination**.

![S3](/images/5.athena/56.png)

8. Check and click **Save**.

![S3](/images/5.athena/57.png)

9. Check and click **Editor** to return.

![S3](/images/5.athena/58.png)

10. Copy the query into the editor, make sure you are using the right table.This query will filter operation **GetObject** whihc have eventsource is **s3.amazonaws.com**. select **Run**.

```sql
SELECT *
FROM cloudtrail_logs_aws_cloudtrail_logs_workshop
WHERE
    eventsource = 's3.amazonaws.com' AND
    eventname in ('GetObject')
```

![S3](/images/5.athena/59.png)

11. Check the result below.

![S3](/images/5.athena/60.png)

12. Finally, run this query to drop the table.

```sql
DROP TABLE `cloudtrail_logs_aws_cloudtrail_logs_workshop`

```

![S3](/images/6.clean/61.png)
