---
description: A rare, but easy, occurence
---

# Updating HTTPS Job Endpoints

We anticipate needing to do this very rarely, and have recently re-architected our product to ensure this is unlikely to occur for the forseable future. That being said, it is possible we will release changes to HTTPS endpoint code. These updates can be brought into your cloud as follows:

## AWS

**OSS Code Repository**: [https://github.com/dragondrop-cloud/ecs-fargate-task-http-trigger](https://github.com/dragondrop-cloud/ecs-fargate-task-http-trigger)

1\) Navigate to the dragondrop-created lambda trigger, and select "Upload from" --> "Amazon S3 location"

<figure><img src="../.gitbook/assets/20230508 Update Lambda Screenshot.png" alt=""><figcaption></figcaption></figure>

2\) Enter the following URL and hit "Save". Now the production code form that repository is within your lambda function. URL:

https://dragondrop-ecs-fargate-task-lambda-trigger-prod.s3.amazonaws.com/dragondrop\_https\_trigger\_lambda.zip

## GCP

**OSS Code Repository**: [https://github.com/dragondrop-cloud/cloud-run-job-http-trigger](https://github.com/dragondrop-cloud/cloud-run-job-http-trigger)

1\) Within the Cloud Run Service hosting your dragondrop endpoint, click "Edit & Deploy New Revision":

<figure><img src="../.gitbook/assets/20230508 Update Cloud Run Service.png" alt=""><figcaption></figcaption></figure>

2\) Without making any changes, scroll to the bottom of the page and hit "Deploy". When using our Terraform module, the container for the cloud service is specified with the `:latest` tag, so this deployment will pull in the newest version of the repo's production container.

## Azure

**OSS Code Repository**: [https://github.com/dragondrop-cloud/container-instance-http-trigger](https://github.com/dragondrop-cloud/container-instance-http-trigger)

1\) Within the Container App instance hosting your dragondrop endpoint, click "Edit and Deploy"

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

2\) Create a "dummy" variable on the container, save and re-deploy. THis deployment will pull in the latest version of the repo's production container.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
