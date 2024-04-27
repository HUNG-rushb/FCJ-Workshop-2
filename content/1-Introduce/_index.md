---
title: "Introduction"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

![FCJ_ws2](/FCJ-Workshop-2/images/1.introduce/aws.png)

**Blue/Green Deployment** is a continuous deployment process that reduces downtime and risk by having two identical production environments, called Blue and Green.

Assume the **Blue** environment is running and the **Green** environment is the new version of your application you will deploy. When developers want to release any new code - a new feature release, a new version of the application, etc. - work on the new version is done in the **Green** environment, while the old version is maintained in Blue. When the new release process is complete, the load balancer will switch all production traffic to the **Green** version, and the **Blue** version is maintained as a backup.

![FCJ_ws2](/FCJ-Workshop-2/images/1.introduce/bg.jpg)

The advantages of the **Blue/Green Deployment** strategy are:

- **Testing parity**: this feature means that tests reflect the reality of production.
- **Deploy anytime**: no downtime means we can deploy anytime. No need to wait for maintenance windows.
- **Instant rollback**: the transition works both ways. If we decide to go back to the previous version, we can switch all users back immediately.
- **Instant switchover**: users are switched to the new version immediately, or nearly so. Everyone sees the latest release at the same time.
- **Hot standby**: Blue-Green can save us from disaster scenarios. Suppose a data center goes offline, we switch to another until the issue is resolved. This will work as long as we have a contingency plan that does not place Blue-Green in the same availability zone.
- **Postmortem**: debugging failed deployments is very difficult with in-place deployments. When faced with downtime, the priority is always to return to normal. Collecting debugging data is secondary, so much valuable information can be lost in the recovery process. Blue-green does not have this problem — Rollbacks always keep the failed deployment intact for analysis.

Along with that, this strategy also has some disadvantages, such as:

- **Consuming more resources** because it needs to maintain 2 environments at the same time when deploying
- **Blue/Green Deployment** requires services on both environments to share a database, in case the new code affects changes in the database structure, a synchronization strategy needs to be built so that both environments can run simultaneously without incident. With this issue, we can use liquibase to build a solution.

With **AWS**, you can operationalize your **Blue/Green deployments** using **Amazon ECS**, an **Application Load Balancer**, and **target groups**.
