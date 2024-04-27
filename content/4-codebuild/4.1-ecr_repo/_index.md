---
title: "Create private repo ECR"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

### Create private repo ECR

1. Go to **Amazon Elastic Container Registry** service. In the left menu, under **Private registry**, choose **Repositories**, then choose **Create repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_1.png)

2. Continue:

- In the **Viability settings** section, choose **Private** (default).
- In the **Repository name** field, enter **`fcj-image-repo`**.
- Scroll down and choose **Create repository**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_2.png)

3. Confirm that the private image repo has been created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/_3.png)

4. Open the source code folder you downloaded in the previous section using your IDE, then:

- Open the **buildspec.yml** file, at line 4, ECR_REPO_NAME, check and replace the repo name **`fcj-image-repo`** with your repo name if you are using a different name, if not, keep it as is.
- Save the file.

![FCJ_ws2](/FCJ-Workshop-2/images/3.codecommit/12.png)
