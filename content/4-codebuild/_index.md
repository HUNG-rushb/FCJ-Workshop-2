---
title: "AWS CodeBuild"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/aws_codebuild.png)

**AWS CodeBuild** is a fully managed build service in the cloud. **CodeBuild** compiles your source code, runs unit tests, and produces artifacts that are ready to deploy. **CodeBuild** eliminates the need to provision, manage, and scale your own build servers. It provides prepackaged build environments for popular programming languages and build tools such as **Apache Maven**, **Gradle**, and more. You can also customize build environments in **CodeBuild** to use your own build tools. **CodeBuild** scales automatically to meet peak build requests.

CodeBuild provides these benefits:

- **Fully managed** – **CodeBuild** eliminates the need to set up, patch, update, and manage your own build servers.
- **On demand** – **CodeBuild** scales on demand to meet your build needs. You pay only for the number of build minutes you consume.
- **Out of the box** – **CodeBuild** provides preconfigured build environments for the most popular programming languages. All you need to do is point to your build script to start your first build.
- **Enables continuous integration and delivery** - **CodeBuild** belongs to a family of AWS developer tools, which you can use to create complete, automated software release workflows for continuous integration and delivery (CI/CD). You can also integrate **CodeBuild** into your existing CI/CD workflow. For example, you can use **CodeBuild** as a worker node for your existing Jenkins server setup for distributed builds.
- **Secure** - With **CodeBuild**, your build artifacts are encrypted with customer-specific keys that are managed by the **AWS Key Management Service (AWS KMS)**. **CodeBuild** is integrated with **IAM**, so you can assign user-specific permissions to your build projects

![FCJ_ws2](/FCJ-Workshop-2/images/4.codebuild/aws_ecr.png)

**Amazon Elastic Container Registry (Amazon ECR)** is an AWS managed container image registry service that is secure, scalable, and reliable. **Amazon ECR** supports private repositories with resource-based permissions using **AWS IAM**. This is so that specified users or **Amazon EC2** instances can access your container repositories and images. You can use your preferred CLI to push, pull, and manage Docker images, Open Container Initiative (OCI) images, and OCI compatible artifacts.

**Amazon ECR** provides the following features:

- Lifecycle policies help with managing the lifecycle of the images in your repositories. You define rules that result in the cleaning up of unused images. You can test rules before applying them to your repository. For more information, see Lifecycle policies.

- Image scanning helps in identifying software vulnerabilities in your container images. Each repository can be configured to scan on push. This ensures that each new image pushed to the repository is scanned. You can then retrieve the results of the image scan. For more information, see Image scanning.

- Cross-Region and cross-account replication makes it easier for you to have your images where you need them. This is configured as a registry setting and is on a per-Region basis. For more information, see Private registry settings.

- Pull through cache rules provide a way to cache repositories in an upstream registry in your private Amazon ECR registry. Using a pull through cache rule, Amazon ECR will periodically reach out to the upstream registry to ensure the cached image in your Amazon ECR private registry is up to date. For more information, see Using pull through cache rules.

### Content

1.  [Create private ECR repo](4.1-ecr_repo/)
2.  [Create CodeBuild project](4.2-build_project/)
3.  [Update CodeBuild role](4.3-role/)
