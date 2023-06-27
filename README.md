---
description: dragondrop.cloud is a managed offering for the cloud-concierge OSS tool.
---

# Welcome

### Why cloud-concierge?

Check out the cloud-concierge docs and repository [here](https://docs.cloudconcierge.io) and [here](https://github.com/dragondrop-cloud/cloud-concierge), respectively. TLDR:

cloud-concierge is an OSS container that allows you to layer functionality on top of an existing Terraform workflow. Namely:

* :white\_check\_mark: Cloud Codification
* :white\_check\_mark: Drift Detection&#x20;
* :white\_check\_mark: Flag the accounts making cloud changes outside of your Terraform workflow
* :white\_check\_mark: Cloud-wide cost estimation, powered by infracost
* :white\_check\_mark: Cloud-wide security scans, powered by tfsec

### Why a managed offering?

cloud-concierge works well when configuring a single execution of the cloud-concierge container. Updating and maintaining multiple environment variable files to configure cloud-concierge is not tractible or enjoyable, and it is difficult to manage scheduled executions for multiple configurations.

dragondrop.cloud makes managing multiple cloud-concierge instances and corresponding execution schedules possible through a user-interface, while still maintaining the self-hosted set up of cloud-concierge.

dragondrop.cloud also provides visual summaries of your cloud environment, stitched together across time and cloud-concierge execution so that your organization can get deeper visibility its cloud footprint across areas like costs, drift, codification, and security.&#x20;
