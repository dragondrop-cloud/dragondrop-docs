---
description: Defensive practices for trust and security at every step.
---

# 🔒 Security

When dealing with information about your cloud posture, as well as Terraform State files, security needs to be at the forefront. That is why dragondrop has engineered security and trust into every step of bringing your cloud into code.

### No information on your current state every leaves your existing tool set.

* dragondrop is a container that is self-hosted by all customers within their cloud.
* No information about your cloud posture or Terraform state ever touches our servers.
* After container execution, all visualizations and identified new resources are exposed through a pull request within your existing VCS.

### dragondrop container only should be given read-only permissions for your cloud environment.

When generating service principals for dragondrop to be able to complete the requisite cloud scanning, read-only permissions should be granted.

### Changes are recommended via Pull Request, never made directly.

The dragondrop container will never directly make changes to your Terraform code base. It will only open a Pull Request in your VCS containing recommended changes and import migration statements.

* Like all other code, your developers have final sign-off and approval into whether or not to merge the suggestions.
* Comments, discussions and changes to the original dragondrop suggestions are all recorded within your VCS.

### Migration statements recorded as code

No more running migrations through the CLI. With dragondrop, all Terraform import migration statements are saved as code within your code base, adding documentation and visibility to state file changes alongside your Terraform code.

### CI/CD Job ensures only imports into Terraform are specified in changes

dragondrop supplies [open-source](https://github.com/dragondrop-cloud/github-action-tfstate-migration) CI/CD processes that follows a `plan` and `apply` structure.

* In order for the `plan` to succeed (and as a result, merging in of dragondrop's suggested changes), no changes outside of Terraform migrations can be set to occur, and specified migrations must be valid.
* In order for the `apply` to succeed, no changes outside of Terraform migrations can be set to occur, and specified migrations must be valid.
