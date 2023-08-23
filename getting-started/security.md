---
description: Defensive practices for trust and security at every step.
---

# 🔒 Security

When dealing with information about your cloud posture, as well as Terraform State files, security needs to be at the forefront. That is why dragondrop has engineered security and trust into every step of ensuring that your cloud is represented fully, and accurately, as code.

<figure><img src="../.gitbook/assets/2023-02-03 Engineered for Security.png" alt=""><figcaption><p>The dragondrop.cloud workflow is engineered for security and trust at every step</p></figcaption></figure>

### (O) Open source by design

The entire cloud-concierge container code is open sourced and availble for viewing and auditing.

### (1) No sensitive data on your cloud posture ever leaves your existing tool set.

* The cloud-concierge container is self-hosted for all executions
* After container execution, all visualizations and identified new resources are exposed through a pull request within your existing VCS
* All telemetry for OSS executions and anonymized data collected from dragondrop-managed jobs can be viewed publicly on GitHub, [here](https://github.com/dragondrop-cloud/cloud-concierge/blob/dev/main/internal/implementations/dragon\_drop/http\_dragondrop\_oss\_methods.go) and [here](https://github.com/dragondrop-cloud/cloud-concierge/blob/dev/main/internal/implementations/dragon\_drop/http\_dragondrop\_managed\_visualization.go), respectfully.

### (2) cloud-concierge only requires read-only permissions for your cloud environment.

When generating service principals for dragondrop to be able to complete the requisite cloud scanning, only read-only permissions should be granted to your cloud environment and the provider remote buckets that store Terraform state files.

### (3) Changes are recommended via Pull Request, never made directly.

The dragondrop container will never directly make changes to your Terraform code base. It will only open a Pull Request in your VCS containing recommended changes and import blocks/import statements.

* Like all other code, your developers have final sign-off and approval into whether or not to merge the suggestions.
* Comments, discussions and changes to the original dragondrop suggestions are all recorded within your VCS.

