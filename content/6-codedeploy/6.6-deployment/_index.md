---
title: "Update and observe deployment"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6.6 </b> "
---

### Update and observe deployment

1. Go back to the source code, open the file **`src/components/Calculator.js`**. Change **line 137** from **Version 1.0** to **2.0**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/33_1.png)

2. Push the code to the repo:

- Run **`git add .`**.
- Run **`git commit -m "Update to 2.0"`** to commit the code locally.
- Run **`git push origin master`** to push the code to the repo on **CodeCommit**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/33_2.png)

3. Go back to the pipeline console, observe the pipeline will be triggered and run the source **Update to 2.0**, and the **Deploy** stage is successfully run.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/34.png)

4. Go to the **ECS** console, view the tasks of the **FCJ_Cluser** cluster, we will see 3 new tasks **Running**, this is the **Green environment**, while the old 3 tasks are the **Blue environment**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/34_1.png)

5. Access **CodeDeploy**, select **Deployments** from the left menu, we will see the deployment of the application is **In progress...**. Click to view details.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/35.png)

6. The image below shows that traffic sent to the **DNS name of FCJ_ALB** is being switched from **Blue environment (90%)** to **Green environment (10%)**, meaning switching from application **Version 1.0** to **2.0**.

- We have configured this to be **10% every minute (step 5 of section 6.4)**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/36.png)

7. Open another tab, or another browser.

- Access **DNS name of FCJ_ALB (step 17 of section 6.4)**.
- Try **hard refresh (Ctrl + R)** a few times.
- You will see that sometimes you receive **Version 1.0**, sometimes it is **Version 2.0**.
- The experiment will be clearer when more % of traffic is switched from **Blue environment** to **Green environment**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/37.png)

8. 6 tasks, 3 tasks for each side **Blue and Green**, will coexist parallelly until the deployment process is successful.

- You can distinguish old and new by viewing the **version of the task definition**. As in the image, the new is **10** and the old is **9**.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/38_1.png)

9. This image shows that all traffic has been switched from **Blue environment (0%)** to **Green environment (100%)**. From here, the **current Blue environment** will be terminated, the **current Green environment** will be promoted to the **new Blue environment**.

- Step 3 of the deployment will **wait 15 minutes (step 13 of section 6.4)** to ensure system stability, if anything causes the deployment to fail, the system will automatically roll back. Otherwise, if everything is stable, the **current Green environment** will be terminated.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/38.png)

10. 3 tasks of **old Blue environment (task definition 9)** have been terminated and 3 new tasks **(task definition 10)** will be promoted to the **new Blue environment**, serving **100%** of user traffic.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/39_1.png)

11. All deployment steps have been successfully completed.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/39.png)

12. Confirm the pipeline has run source **Update to 2.0** successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/6.codedeploy/40.png)

### So you have completed a **Blue/Green deployment pipeline** using **AWS CodePipeline**.
