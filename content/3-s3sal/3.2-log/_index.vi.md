---
title: "Kiểm tra log"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3. </b> "
---

### Truy cập file và kiễm tra log

1. Mở một tab ẩn danh mới và nhập URL truy cập tới file chúng ta đã lưu.

2. Quay về giao diện buckets, chọn bucket **logging-workshop-destination**, chờ khoảng 15 phút, refresh lại bucket.

3. Chúng ta sẽ thấy những file log đã được tạo ra. Chọn vào 1 file log.

4. Chúng ta có thể thấy thông tin file log này. Chọn **Download** và mở file log ra

5. File log sẽ có cấu trúc như sau:

```
b07c1e6c73fc3be646182d0400a50638e0703b6352275b2d165aa35f9791c572 logging-workshop [03/Mar/2024:12:52:26 +0000] 118.69.159.186 arn:aws:iam::928738046450:user/hung 2ET0N53Y32R632Q5 REST.GET.OWNERSHIP_CONTROLS - "GET /logging-workshop?ownershipControls= HTTP/1.1" 200 - 193 - 53 53 "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.12.488 Linux/5.10.209-175.858.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.372-b08 java/1.8.0_372 vendor/Oracle_Corporation cfg/retry-mode/standard" - xqa7XzBU4q1xnx4NmkVBFhDsnt0jk07Slo9F3j2kvD0/6zSveFBzQ5t+Zrfs/me6L4epr6/dG3k= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.ap-southeast-1.amazonaws.com TLSv1.2 - -
b07c1e6c73fc3be646182d0400a50638e0703b6352275b2d165aa35f9791c572 logging-workshop [03/Mar/2024:12:52:28 +0000] 118.69.159.186 arn:aws:iam::928738046450:user/hung YP9K97RHY7C5JPBC REST.GET.OBJECT_TAGGING S3_logging_workshop.txt "GET /logging-workshop/S3_logging_workshop.txt?tagging= HTTP/1.1" 200 - 115 - 13 10 "-" "S3Console/0.4, aws-internal/3 aws-sdk-java/1.12.488 Linux/5.10.209-175.858.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.372-b08 java/1.8.0_372 vendor/Oracle_Corporation cfg/retry-mode/standard" - nGxxv80fXE5xGWiS6C7OIg7/ncxoVho61Lmw9+qyveqdOBbiqRD4HJZf8qU90j0IeUXNGmwcSwA= SigV4 ECDHE-RSA-AES128-GCM-SHA256 AuthHeader s3.ap-southeast-1.amazonaws.com TLSv1.2 - -
```
