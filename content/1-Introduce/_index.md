---
title: "Introduction"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

When you use logging with Amazon S3, you can record actions taken by users, and services on your Amazon S3 resources. You can then use the log records for auditing and compliance purposes.

![S3log](/images/1.introduce/10.png)

You can log Amazon S3 actions using server access logs or AWS CloudTrail logs.

**Server access logging** is a mechanism that provides detailed records for requests made to an S3 bucket.

Server access logging is disabled by default. Enable server access logging to start receiving logs. Log records are generally delivered within a few hours and it is rare to lose log records. There is no charge for enabling access logging, nor for PUT operations for log files. You are only charged for storage of the logs and for GET operations on the files. You can use object lifecycle management to minimize storage costs.

![S3sal](/images/1.introduce/11.png)

AWS CloudTrail is a service that provides records of actions taken by a user, role, or service in your AWS Account. You can use CloudTrail to audit your account by logging and monitoring all activity. You can also use CloudTrail to detect unusual activity in your account.

Logging Amazon S3 actions with AWS CloudTrail helps keep your account secure by providing access auditing and analysis.

![S3ct](/images/1.introduce/12.png)

**Comparison**

| Log properties                                                                                       | AWS CloudTrail | Amazon S3 server logs |
| ---------------------------------------------------------------------------------------------------- | :------------: | :-------------------: |
| Can be forwarded to other systems (Amazon CloudWatch Logs, Amazon CloudWatch Events)                 |    **Yes**     |          No           |
| Deliver logs to more than one destination (for example, send the same logs to two different buckets) |    **Yes**     |          No           |
| Turn on logs for a subset of objects (prefix)                                                        |    **Yes**     |          No           |
| Cross-account log delivery (target and source bucket owned by different accounts)                    |    **Yes**     |          No           |
| Integrity validation of log file by using digital signature or hashing                               |    **Yes**     |          No           |
| Default or choice of encryption for log files                                                        |    **Yes**     |          No           |
| Object operations (by using Amazon S3 APIs)                                                          |    **Yes**     |        **Yes**        |
| Bucket operations (by using Amazon S3 APIs)                                                          |    **Yes**     |        **Yes**        |
| Searchable UI for logs                                                                               |    **Yes**     |          No           |
| Fields for Object Lock parameters, Amazon S3 Select properties for log records                       |    **Yes**     |          No           |

Amazon Athena is an interactive query service that makes it easy for you to analyze data in Amazon S3 using standard SQL. You do not need to manage any infrastructure with Athena, and you pay only for the queries that you run.

Once you enable server access logs and store them in your target S3 bucket, you might want to analyze or search through them. Logs are not automatically analyzed by Amazon S3, and you might have a lot of data. To analyze all your Amazon S3 data, you can use Amazon Athena.

![S3athena](/images/1.introduce/13.png)
