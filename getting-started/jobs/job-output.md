# Job Output

Note that "external resource" refers to a cloud resource that is outside of Terraform control but living within your public cloud.

### New Terraform Code for External Resources

Each identified external resource has Terraform code generated for it and placed into the directory associated with the workspace that dragondrop has identified as most appropriate for the resource. This new Terraform code is generated in a file called "dragondrop.tf", allowing you to take the configuration and place it within your organized Terraform files with desired syntax modifications (modules, loops, etc.). At the top of each resource is information on the Cloud Actor who created and most recently modified the resource.

<figure><img src="../../.gitbook/assets/202230315_resource_output.png" alt=""><figcaption><p>New Terraform Code for external resources, along with the service principals and users that created the resources in the first place.</p></figcaption></figure>

### Migration Statements for Importing Resources

Each identified external resource also has a matching state migration statement to import cloud resources generated within the Pull Request. This allows you to store all resource imports as code within your VCS instead of running state migration commands arbitrarily and without record through the CLI.

<figure><img src="../../.gitbook/assets/20230315_migration_import_statement_output.png" alt=""><figcaption><p>Automated PR from dragondrop, example of generated migration statements to import external resources.</p></figcaption></figure>

### State of Cloud Report and Cloud Actor Identification

Each Pull Request outputs via a PR comment a "State of Cloud Report" which provides a high level summary of the drifted and new-to-Terraform resources identified by dragondrop. It also outputs a summary of the Cloud Actors that made changes outside of your Terraform workflow, allowing you to close the loop on Terraform drift.

<figure><img src="../../.gitbook/assets/20230315_cloud_actor_screen_shot.png" alt=""><figcaption><p>Surfaced Cloud Actors responsible for changes outside of Terraform control.</p></figcaption></figure>

### Drift Within Terraform-Managed Resources

Cleaner than parsing `terraform plan`, each job outputs the specific resource attributes that have drifted for resources that are already managed by Terraform. If this is the only type of drift that your organization would like to identify and surface, that is [configurable within your job](managed-drift-only-mode.md).

<figure><img src="../../.gitbook/assets/20230514 managed resource drift.png" alt=""><figcaption></figcaption></figure>

### Resource Cost Calculations

Within the State of Cloud Report, as well as for individual resources, dragondrop provides detailed cost calculations. Provides users a single pane for their cloud costs (both controlled by Terraform and uncontrolled) within a Pull Request. Cost calculations are powered by a native [Infracost](https://github.com/infracost/infracost) integration.

<figure><img src="../../.gitbook/assets/20230411 Monthly Cost Breakdown.png" alt=""><figcaption><p>Keep all cloud information in one place with cloud cost estimation built into every dragondrop Job execution.</p></figcaption></figure>

### Security Risk Surfacing

Identify for all scanned resources, by resource instance, security risks within your cloud.

<figure><img src="../../.gitbook/assets/20230515 - Security Risk Idenitification.png" alt=""><figcaption><p>dragondrop can serve as a single pane for codification, drift detection, cost estimation, and security risk identification.</p></figcaption></figure>
