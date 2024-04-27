---
title: "Update code"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 6.3 </b> "
---

### Update code

1. Access **AWS ECS**, go to **Task definitions**, and select the task **FCJ_Task_Definition** that you have created. Select the **JSON** tab, then **Copy to clipboard**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_1.png)

2. From the source code, open the file **`taskdef.json`** in your IDE. Replace the entire content in that file with the task definition you copied in step 1.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_2.png)

3. At line 6, where the key **image** is located, replace its value with **`<IMAGE1_NAME>`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_3.png)

4. Scroll down to the end or search in the IDE for the term **`tags`**, you will find **"tags": []**, delete it.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_4.png)

5. Open the file **`appspec.yml`**, at line 8, **ContainerName**, replace the value with **`fcj_container`**. This is the container name you set in step **5** of section **6.2**, you can also find **"name": "fcj_container"** in the task definition in the file **`taskdef.json`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_5.png)

6. Push the code to the repo:

- Run **`git add .`**.
- Run **`git commit -m "Update config"`** to commit the code locally.
- Run **`git push origin master`** to push the code to the repo on **CodeCommit**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_6.png)

7. Open your pipeline and observe. After all stages are successful, access **AWS S3**, find and select the bucket **codepipeline-us-east-1-......**. This is the bucket that **CodePipeline** creates to store artifacts. Each region will have a corresponding bucket for the pipeline region.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_7.png)

8. Select the folder named **`FCJ_Pipeline`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_8.png)

9. Select the folder **`BuildArtif`**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_9.png)

10. Click on the **Last modified** tab to sort by time, select the most recent item, click **Download** to download.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_10.png)

11. Unzip and check to confirm that the content is correct with what you have edited in the steps above. If so, our artifact has been built successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/9_11.png)
