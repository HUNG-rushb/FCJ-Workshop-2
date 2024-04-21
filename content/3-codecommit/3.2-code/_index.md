---
title: "Push Code to CodeCommit Repository"
date: "`r Sys.Date()`"
weight: 2
chapter: true
pre: " <b> 3.2 </b> "
---

### Download source code

1. Access this link `https://github.com/HUNG-rushb/React-Calculator/releases/tag/v1` and download the source code. This is a simple Calculator App written in React that we will use to deploy.

![FCJ_ws2](/images/3.codecommit/5.png)

2. Download and extract it to the directory you want to work in. Check if the files are complete as shown below.

![FCJ_ws2](/images/3.codecommit/6.png)

### Push code to CodeCommit repo

3. Inside that directory:

- Run **`git init`** to create a git repo.
- Run **`git remote add origin PASTE_HTTPS_REPO_LINK_HERE`**, replace **PASTE_HTTPS_REPO_LINK_HERE** with the HTTPS link you copied in the previous section.
- Run **`git add .`**.
- Run **`git commit -m "init"`** to commit the code locally (not in the image).

![FCJ_ws2](/images/3.codecommit/7.png)

4. Continue:

- Run **`git push origin master`** to push the code to the repo on **CodeCommit**.
- Git will ask you for **Username** and **Password**, this is the credentials in the codecommit credentials file that we created in the **Create HTTPS Git Credentials for CodeCommit** section.
- Open the file credentials, copy **username** and **password** into cmd.
- Enter and confirm that the code has been successfully pushed.

![FCJ_ws2](/images/3.codecommit/9.png)

5. Return to the tab you are opening **AWS**, move to the **CodeCommit** service and into your repo, you will see the code has been successfully pushed.

![FCJ_ws2](/images/3.codecommit/10.png)

6. On the left menu, choose **Commits** and check the most recent commit is yours, in the image is **init**.

![FCJ_ws2](/images/3.codecommit/11.png)
