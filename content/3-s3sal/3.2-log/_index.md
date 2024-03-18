---
title: "Check logs"
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: " <b> 3.2 </b> "
---

### Truy cập file và kiễm tra log

1. Open new private tab and acces the file.

2. In buckets console, select bucket **logging-workshop-destination**, wait about 15 minutes, refresh the bucket.

![CreateBucket](/images/3.connect/37.png)

3. We can see there are logs there, select one.

![CreateBucket](/images/3.connect/38.png)

4.  Select **Download** and open it.

![CreateBucket](/images/3.connect/39.png)

5. the log file will looks like below:

```
b07c1e6c73fc3be646182d0400a50638e0703b6352275b2d165aa35f9791c572 logging-workshop [03/Mar/2024:12:52:26 +0000] 118.69.159.186 arn:aws:iam::928738046450:user/hung 2ET0N53Y32R632Q5 REST.GET.OWNERSHIP_CONTROLS - "GET /logging-workshop?ownershipControls= HTTP/1.1" 200 - 193 - 53 53 "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.12.488 Linux/5.10.209-175.858.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.372-b08 java/1.8.0_372 vendor/Oracle_Corporation cfg/retry-mode/standard" - xqa7XzBU4q1xnx4NmkVBFhDsnt0jk07Slo9F3j2kvD0/6zSveFBzQ5t+Zrfs/me6L4epr6/dG3k= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.ap-southeast-1.amazonaws.com TLSv1.2 - -
b07c1e6c73fc3be646182d0400a50638e0703b6352275b2d165aa35f9791c572 logging-workshop [03/Mar/2024:12:52:28 +0000] 118.69.159.186 arn:aws:iam::928738046450:user/hung YP9K97RHY7C5JPBC REST.GET.OBJECT_TAGGING S3_logging_workshop.txt "GET /logging-workshop/S3_logging_workshop.txt?tagging= HTTP/1.1" 200 - 115 - 13 10 "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.12.488 Linux/5.10.209-175.858.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.372-b08 java/1.8.0_372 vendor/Oracle_Corporation cfg/retry-mode/standard" - nGxxv80fXE5xGWiS6C7OIg7/ncxoVho61Lmw9+qyveqdOBbiqRD4HJZf8qU90j0IeUXNGmwcSwA= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.ap-southeast-1.amazonaws.com TLSv1.2 - -
```
