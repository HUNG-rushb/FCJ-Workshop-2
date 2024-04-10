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

2. for **Storage location**, select bucket **aws-cloud-trail-logs-workshop** which we are using to store logs then select **Create table**.

3. Confirm Athena table **cloudtrail_logs_aws_cloudtrail_logs_workshop** created.

4. Find select service **Athena**, then select **Launch query editor**.

5. If this is the first time you use Athena, select **Edit settings**, if not, skip to step 10.

6. Click **Browse S3**.

7. Select 1 bucket to store query's result, here we choose bucket **logging-workshop-destination**.

8. Check and click **Save**.

9. Check and click **Editor** to return.

10. Copy the query into the editor, make sure you are using the right table.This query will filter operation **GetObject** whihc have eventsource is **s3.amazonaws.com**. select **Run**.

```sql
SELECT *
FROM cloudtrail_logs_aws_cloudtrail_logs_workshop
WHERE
    eventsource = 's3.amazonaws.com' AND
    eventname in ('GetObject')
```

11. Check the result below.

12. Finally, run this query to drop the table.

```sql
DROP TABLE `cloudtrail_logs_aws_cloudtrail_logs_workshop`

```
