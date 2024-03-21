---
title: "Edit policy "
date: "`r Sys.Date()`"
weight: 4
chapter: true
pre: " <b> 2.4 </b> "
---

### Thêm policy cho bucket

1. In **S3** console, select **logging-workshop** bucket.

![CreateBucket](/Workshop-1/images/2.prerequisite/30.png)

2. Select **Permissions** tab.

![CreateBucket](/Workshop-1/images/2.prerequisite/31.png)

3. for **Bucket policy**, select **Edit**.

![CreateBucket](/Workshop-1/images/2.prerequisite/32.png)

4. Insert:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::logging-workshop/*"
    }
  ]
}
```

![CreateBucket](/Workshop-1/images/2.prerequisite/33.png)

5. Chọn **Save changes**

![CreateBucket](/Workshop-1/images/2.prerequisite/34.png)

6. Confirm updated successfully

![CreateBucket](/Workshop-1/images/2.prerequisite/35.png)
