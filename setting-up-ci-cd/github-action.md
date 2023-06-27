---
description: CI/CD Support within GitHub Actions Pipelines.
---

# GitHub Action

### Note: You can [skip this section](../getting-started/setting-up-ci-cd.md#terraform-post-1.5.0) if running your managed cloud-concierge containers with Terraform v1.5.0 or greater

Set up our [GitHub Action](https://github.com/dragondrop-cloud/github-action-tfstate-migration) within the code repositories in which dragondrop will be opening Pull Requests.  but at a high-level the CI/CD job performs the following operations:

* Install your desired version of Terraform
* If in `plan` mode, check to make sure that the only changes to Terraform in the current pull request are to import external resources into Terraform control, and that those imports are correctly specified.
* If in `apply` mode, perform everything from the `plan` step and then run the import statements as code.

We recommend using `plan` mode during continuous integration, and after merge, use `apply` mode.

Given that some of the needed environment variables are a bit involved, we also offer support for auto-validation within the web application. This allows faster cycle time in making sure your environment variables are correctly formatted. All environment variables are evaluated client-side.

For further details on implementing the Action itself, the README associated with the Action is well documented.
