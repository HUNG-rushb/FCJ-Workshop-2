---
title: "Cập nhật quyền cho codebuild role"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

### Cập nhật quyền cho codebuild role

1. 1

![FCJ_ws2](/images/4.codebuild/21.png)

1. 1

![FCJ_ws2](/images/4.codebuild/22.png)

1. 1

![FCJ_ws2](/images/4.codebuild/23.png)

1. 1

![FCJ_ws2](/images/4.codebuild/24.png)

1. 1

![FCJ_ws2](/images/4.codebuild/25.png)

1. 1

![FCJ_ws2](/images/4.codebuild/26.png)

1. 1

![FCJ_ws2](/images/4.codebuild/27.png)

1. 1

![FCJ_ws2](/images/4.codebuild/28.png)

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
