# FAQs

### How long does it take to self host dragondrop?

With our provided [open-source Terraform modules](https://registry.terraform.io/namespaces/dragondrop-cloud), you can spin up the required infrastructure in minutes. Configuring the six needed environment variables via secrets in your cloud can take less than 15 minuts. We conservatively estimate that the first Job in an organization will take less than 45 minutes in total for a complete self-hosting.

### Does information on my cloud touch dragondrop servers?

No. Since dragondrop is hosted within your cloud, no information about your Cloud Posture or Terraform state ever touches our servers. All information stays within your existing cloud environment and version control system.

### Can dragondrop engineers access the dragondrop container once deployed in my cloud?

No. We have no access to the hosted container in your environment (this can be verified by viewing the configuration of the [Open Source Terraform Modules](https://registry.terraform.io/namespaces/dragondrop-cloud) used to host our container in your cloud).

### Can I validate environment variable formats outside of the executable container?

Yes. Our web application includes a client-side variable format validator to help you quickly ensure that your environment variables are appropriately formatted prior to kicking off a Job.
