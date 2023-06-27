---
description: Serverless container compute with an https endpoint.
---

# Self-Hosted Runners

To provide you with the best possible security, all dragondrop customers (including those using our forever free tier!) deploy a managed [cloud-concierge](https://github.com/dragondrop-cloud/cloud-concierge/blob/dev/main/internal/implementations/dragon\_drop/http\_dragondrop\_managed\_visualization.go) instance into their own cloud environment.

Because cloud-concierge is a containerized executable, all that is needed within your cloud is serverless compute capable of running a container, along with an HTTPS endpoint that dragondrop can make calls to for invoking said serverless compute.

For more details on deployment of managed cloud-concierge containers into your environment, please see [Deploying To Your Cloud](broken-reference).
