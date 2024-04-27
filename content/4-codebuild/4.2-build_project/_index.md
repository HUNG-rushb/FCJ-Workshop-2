---
title: "Create CodeBuild Project"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### Create CodeBuild Project

1. Move to the **CodeBuild** service, on the left menu choose **Build projects**, then select **Create project**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/1.png)

2. Then:

- In the **Project name** field, enter **`FCJ_Build_Project`**.
- In the **Source 1 - Primary** field, choose provider **AWS CodeCommit**, then select repo **FCJ_Repo**.
- In the **Branch** field, choose **master**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/2.png)

3. Open the **Additional configuration** section, then tick **Enable this flag if you want to build Docker images or want your builds to get elevated privileges**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/3.png)

4. In the **Buildspec** section, tick **Use a buildspec file**, enter **`buildspec.yml`**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/4.png)

5. Scroll down and choose **Create build project**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/5.png)

6. Confirm that the build project has been created successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/6.png)
