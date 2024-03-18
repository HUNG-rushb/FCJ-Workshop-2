---
title: "Update logging permission "
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: " <b> 2.2 </b> "
---

### Cập nhật quyền tạo log cho S3 log delivery group

1. Return to bucket console, select bucket **logging-workshop-destination**. Scroll down to section **Object Ownership**, select **Edit**

![CreateBucket](/images/2.prerequisite/41-5.png)
![CreateBucket](/images/2.prerequisite/42.png)

2.  Select **ACLs enabled**, confirm **I acknowledge that ACLS will be restored.**, select **Save changes**. This will make everythin in the **Access control list (ACL)** can create object.

![CreateBucket](/images/2.prerequisite/43.png)

3. Scroll down to section **Access control list (ACL)**, select **Edit**.

![CreateBucket](/images/2.prerequisite/44.png)

4. At **S3 log delivery group**, select **Write**, then **Save changes**.

![CreateBucket](/images/2.prerequisite/45.png)

5. Confrim **Write** for **S3 log delivery group**.

![CreateBucket](/images/2.prerequisite/46.png)

6.  Return to bucket console.
