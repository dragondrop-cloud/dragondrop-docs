---
description: >-
  Because no sensitive data touches dragondrop servers, sensitive job
  parameterization occurs through environment variables attached to the compute
  running the dragondrop container.
---

# Environment Variables

## Resources

* All non-sensitive variables are specified via the dragondrop user interface for cloud-concierge job management.
* The dragondrop management platform offers a client-side environment variable validator to quickly check whether your environment variables are formatted correctly. This can be found [here](https://app.dragondrop.cloud/env-var-validator).

## Variable Descriptions

### cloud-concierge Env Vars

`CLOUDCONCIERGE_ORGTOKEN`

* **Description**: Token for your dragondrop organization.
  * Sign-into the [dragondrop management platform](https://app.dragondrop.cloud) through GitHub social sign-on. You will be redirected to the "Organization" tab, where you will have the opportunity to copy your org token.
* **Example**: cco-my-org-token

### Cost Calculation Tokens Job Env Vars

`CLOUDCONCIERGE_INFRACOSTAPITOKEN`

* **Description**: Registered Infracost API token. Can be either hosted or self hosted.
  * Docs on Infracost API token registration can be found [here](https://github.com/infracost/cloud-pricing-api).
* **Example**: "my-infracost-api-token"

### Scanning Your Cloud Env Vars

`CLOUDCONCIERGE_DIVISIONCLOUDCREDENTIALS`

* **Description**: Mapping between the name of a division of a public cloud provider and the corresponding credential for access to your cloud environment.
  * A division for AWS is an account name, for Azure it is a resource group, and for GCP it is a project.
  * _AWS Example_: A service account credentials key map of the format {awsAccessKeyID: "", awsSecretAccessKey:""}
  * _Google Example_: A service account key with new-lines and tabs removed.
  * _Azure Example_: A service account identifying JSON dictionary
* **Structure**: "{google-divisionName1}:{serviceAccount1}"
* **Example**: my-gcp-project:{service account secret key},my-aws-account:{awsAccessKeyID": "MYKEYID","awsSecretAccessKey": "MYSECRETKEYID"},my-azure-resource-group:{"client\_id":"","client\_secret":"","tenant\_id":"","subscription\_id":""}
* **Structure**: "{google-divisionName1}:{serviceAccount1}"
*   **Example**: my-gcp-project:{service account secret key},my-aws-account:{awsAccessKeyID": "MYKEYID","awsSecretAccessKey": "MYSECRETKEYID"}



### Version Control System (VCS) Env Vars&#x20;

`CONCIERGE_VCSTOKEN`

* **Description**: Personal access token for the VCS provider specified. Allows the containerized executable to interact with the VCS provider to open a pull request containing new resources and needed migrations.
  * For GitHub, should only be provided "Repo" permissions.
* **Example**: "ghp\_my-github-access-token"

### Terraform Cloud Env Vars  (if selected as your state backend)

`CONCIERGE_TERRAFORMCLOUDTOKEN`

* **Description**: Terraform cloud team token for accessing remote workspaces.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"
