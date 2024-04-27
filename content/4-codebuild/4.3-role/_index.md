---
title: "Update CodeBuild Role"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

### Update CodeBuild Role

1. Access the **IAM** service:

- On the left menu, choose **Roles**.
- Search for **`codebuild`**.
- Select the codebuild role corresponding to your project.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/21.png)

2. Choose **Add permissions**, then **Create inline policy**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/22.png)

3. Copy and paste the policy below into the **Policy editor**. Then scroll down and choose **Next**.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ecr-public:GetAuthorizationToken",
        "sts:GetServiceBearerToken",
        "ecr-public:BatchCheckLayerAvailability",
        "ecr-public:GetRepositoryPolicy",
        "ecr-public:DescribeRepositories",
        "ecr-public:DescribeRegistries",
        "ecr-public:DescribeImages",
        "ecr-public:DescribeImageTags",
        "ecr-public:GetRepositoryCatalogData",
        "ecr-public:GetRegistryCatalogData"
      ],
      "Resource": "*"
    }
  ]
}
```

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/23.png)

4. In the **Policy name** field, enter **FCJ_ECR_Public_Access**. Then press **Create policy**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/24.png)

5. Confirm that the policy has been added successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/25.png)

6. Continue to choose **Add permissions**, then **Attach policies**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/26.png)

7. Search for **AmazonEC2ContainerRegistryFullAccess**. Select and press **Add permissions**.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/27.png)

8. Confirm that the policy has been added successfully.

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/28.png)
