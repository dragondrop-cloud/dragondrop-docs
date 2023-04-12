---
description: >-
  Because no information about your cloud touches dragondrop servers, job
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

* `DRAGONDROP_DIVISIONTOPROVIDER`
  * **Description**: Mapping between the name of a division of a public cloud provider and the corresponding cloud provider name.
    * A division for AWS is an account name, for Azure is a resource group, and for GCP is a project.
    * Provider names must match the Terraform provider name (aws, azurern, google, etc.).
  * **Structure**: "{divisionName1}:{provider1},...,{divisionNameN}:{provider1}"
  * **Example**: "my-aws-project:aws,my-gcp-project:google"

`DRAGONDROP_DIVISIONCLOUDCREDENTIALS`

* **Description**: Mapping between the name of a division of a public cloud provider and the corresponding read-only credential.
  * A division for AWS is an account name, for Azure is a resource group, and for GCP is a project.
  * _Google_: A service account key with new-lines and tabs removed.
* **Structure**: "{google-divisionName1}:{serviceAccount1}"
* **Example**: "my-gcp-project:{service account secret key}"

### Version Control System (VCS) Env Vars&#x20;

`DRAGONDROP_VCSTOKEN`

* **Description**: Personal access token for the VCS provider specified. Allows the containerized executable to interact with the VCS provider to open a pull request containing new resources and needed migrations.
  * For GitHub, should only be provided "Repo" permissions.
* **Example**: "ghp\_my-github-access-token"

`DRAGONDROP_VCSUSER`

* **Description**: Username of the account associated with the Version Control System.
* **Example**: "MyUserName"

### Pull Request Env Vars

`DRAGONDROP_WORKSPACETODIRECTORY`

* **Description**: Map between Terraform Workspace name and the relative directory within the code repository where that workspace is defined via Terraform.
* **Structure**: "{workSpace1}:/{relativeDirPath1},...,{workspaceN}:/{relativeDirPathN}"
  * Each relative directory must start with a backslash and end without a backlash.
* **Example**: "workspace-1:/path/to/workspace-one/,workspace-2:/path/to/workspace-two/"

### Terraform Cloud Env Vars

`DRAGONDROP_TERRAFORMCLOUDTOKEN`

* **Description**: Name of the Terraform Cloud Organization where workspaces are located.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"
