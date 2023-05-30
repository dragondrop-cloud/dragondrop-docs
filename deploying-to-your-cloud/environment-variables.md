---
description: >-
  Because no sensitive data touches dragondrop servers, sensitive job
  parameterization occurs through environment variables attached to the compute
  running the dragondrop container.
---

# Environment Variables

### dragondrop Job Env Vars

`DRAGONDROP_JOBTOKEN`

* **Description**: Token for the current dragondrop Job.
  * Go to "Jobs" page in the web application. Select "Details" for the Job of interest, and copy the token displayed.
* **Example**: "my-dragondrop-job-token"

### Cost Calculation Tokens Job Env Vars

`DRAGONDROP_INFRACOSTAPITOKEN`

* **Description**: Registered Infracost API token. Can be either hosted or self hosted.
  * Docs on Infracost API token registration can be found [here](https://github.com/infracost/cloud-pricing-api).
* **Example**: "my-infracost-api-token"

### Scanning Your Cloud Env Vars

`DRAGONDROP_DIVISIONCLOUDCREDENTIALS`

* **Description**: Mapping between the name of a division of a public cloud provider and the corresponding read-only credential.
  * A division for AWS is an account name, for Azure is a resource group, and for GCP is a project.
  * _AWS_: A service account credentials key map of the format {awsAccessKeyID: "", awsSecretAccessKey:""}
  * _Google_: A service account key with new-lines and tabs removed.
* **Structure**: "{google-divisionName1}:{serviceAccount1}"
*   **Example**: my-gcp-project:{service account secret key},my-aws-account:{awsAccessKeyID": "MYKEYID","awsSecretAccessKey": "MYSECRETKEYID"}



### Version Control System (VCS) Env Vars&#x20;

`DRAGONDROP_VCSTOKEN`

* **Description**: Personal access token for the VCS provider specified. Allows the containerized executable to interact with the VCS provider to open a pull request containing new resources and needed migrations.
  * For GitHub, should only be provided "Repo" permissions.
* **Example**: "ghp\_my-github-access-token"

### Terraform Cloud Env Vars

`DRAGONDROP_TERRAFORMCLOUDTOKEN`

* **Description**: Terraform cloud team token for accessing remote workspaces.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"
