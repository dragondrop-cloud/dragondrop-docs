---
description: >-
  Because no information about your cloud touches dragondrop servers, job
  parameterization occurs through environment variables attached to the compute
  running the dragondrop container.
---

# Environment Variables

### dragondrop Job Env Vars

`DRAGONDROP_JobToken`

* **Description**: Token for the current dragondrop Job.
  * Go to "Jobs" page in the web application. Select "Details" for the Job of interest, and copy the token displayed.
* **Example**: "my-dragondrop-job-token"

### Scanning Your Cloud Env Vars

* `DRAGONDROP_DivisionToProvider`
  * **Description**: Mapping between the name of a division of a public cloud provider and the corresponding cloud provider name.
    * A division for AWS is an account name, for Azure is a resource group, and for GCP is a project.
    * Provider names must match the Terraform provider name (aws, azurern, google, etc.).
  * **Structure**: "{divisionName1}:{provider1},...,{divisionNameN}:{provider1}"
  * **Example**: "my-aws-project:aws,my-gcp-project:=google"

`DRAGONDROP_DivisionCloudCredentials`

* **Description**: Mapping between the name of a division of a public cloud provider and the corresponding read-only credential.
  * A division for AWS is an account name, for Azure is a resource group, and for GCP is a project.
  * _Google_: A service account key with new-lines and tabs removed.
* **Structure**: "{google-divisionName1}:{serviceAccount1}"
* **Example**: "my-gcp-project:{service account secret key}"

`DRAGONDROP_Providers`

* **Description**: Mapping between the name of Terraform providers, and the version of the providers desired.
  * Provider names must match the Terraform provider name (aws, azurern, google, etc.).
* **Structure**: "{provider1}:{version1},...,{providerN}:{versionN}"
* **Example**: "aws:\~>4.3.0,google:4.27.0"

`DRAGONDROP_TerraformVersion`

* **Description**: String for the version of Terraform to use for importing resources.
  * Must be a valid version of Terraform.
* **Structure**: "{terraformVersion}"
* **Example**: "1.2.4"

### Version Control System (VCS) Env Vars&#x20;

`DRAGONDROP_VCSSystem`

* **Description**: Name of the VCS used, all lowercase.
  * Currently only GitHub is supported.
* **Example**: "github"

`DRAGONDROP_VCSRepo`

* **Description**: Full URL of the code repository within the specified VCS System where recommended changes will be placed via Pull Request.
  * Currently only GitHub-hosted repositories are supported.
* **Example**: "https://github.com/my-organization/my-repo"

`DRAGONDROP_VCSBaseBranch`

* **Description**: Name of the base branch to clone from the VCS Repo. Pull requests are opened to merge into this base branch
  * Should be a stable branch that will not be removed. We recommend using "develop" or the equivalent.
* **Structure**: "{branch name}"
* **Example**: "develop"

`DRAGONDROP_VCSToken`

* **Description**: Personal access token for the VCS provider specified. Allows the containerized executable to interact with the VCS provider to open a pull request containing new resources and needed migrations.
  * For GitHub, should only be provided "Repo" permissions.
* **Example**: "ghp\_my-github-access-token"

`DRAGONDROP_VCSUser`

* **Description**: Username of the account associated with the Version Control System.
* **Example**: "MyUserName"

### Pull Request Env Vars

`DRAGONDROP_RelativeDirectoryMarkdown`

* **Description**: Relative directory within the code repository to which the markdown visualizations will be saved.
* **Structure**: "/{relativeDir1}/.../{relativeDirN}"
  * Must start with a backslash and end without a backslash
* **Example**: "/where/to/output/markdown/directory"

`DRAGONDROP_WorkspaceToDirectory`

* **Description**: Map between Terraform Workspace name and the relative directory within the code repository where that workspace is defined via Terraform.
* **Structure**: "{workSpace1}:/{relativeDirPath1},...,{workspaceN}:/{relativeDirPathN}"
  * Each relative directory must start with a backslash and end without a backlash.
* **Example**: "workspace-1:/path/to/workspace-one/,workspace-2:/path/to/workspace-two/"

`DRAGONDROP_MigrationHistoryStorage`

* **Description**: JSON object containing information on where migration history data should be stored.
* **Structure**: {"storageType": \["gcs"|"s3"], "bucket": {bucketName}, "region": {my-region\}}
  * Currently only Google Cloud Storage (gcs) or (s3) are supported as stores of migration histories.
* **Example**: {"storageType": "s3", "bucket": "my-migration-history-bucket", "region": "us-east1"}

### Terraform Cloud Env Vars

`DRAGONDROP_StateBackend`

* **Description**: Name of the remote state backend management system.
  * Currently only `TerraformCloud` is supported.
* **Example**: "TerraformCloud"

`DRAGONDROP_TerraformCloudOrganization`

* **Description**: Name of the Terraform Cloud Organization where workspaces are located.
* **Example**: "my-tf-cloud-org"

`DRAGONDROP_TerraformCloudToken`

* **Description**: Name of the Terraform Cloud Organization where workspaces are located.
  * Should be a Terraform Cloud Team Token.
* **Example**: "my-tf-cloud-team token"

### Messaging Service

`DRAGONDROP_MessageService`

* **Description**: Name of the messaging service to which alerts around job execution and completion will be sent.
  * Currently only "Slack" is supported as an option.
* **Example**: "Slack"

`DRAGONDROP_MessageServiceToken`

* **Description**: Token for permissions to push alerts to the selected message service.
* **Example**: "my-slack-example-token"

`DRAGONDROP_Channel`

* **Description**: Name of the channel to which alerts about Job execution and completion should be sent.
  * Should start with a "#"
* **Example**: "#my-alert-channel"
