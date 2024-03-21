---
title: "Edit policy "
date: "`r Sys.Date()`"
weight: 4
chapter: true
pre: " <b> 2.4 </b> "
---

### Thêm policy cho bucket

1. In **S3** console, select **logging-workshop** bucket.

2. Select **Permissions** tab.

3. for **Bucket policy**, select **Edit**.

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

5. Chọn **Save changes**

6. Confirm updated successfully
