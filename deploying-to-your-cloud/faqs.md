# FAQs

### How long does it take to self host dragondrop?

With our provided [open-source Terraform modules](https://registry.terraform.io/namespaces/dragondrop-cloud), you can spin up the required infrastructure in minutes. Configuring the six needed environment variables via secrets in your cloud can take less than 15 minuts. We conservatively estimate that the first Job in an organization will take less than 30 minutes in total for a complete self-hosting.

### Does information on my cloud touch dragondrop servers?

Only highly anonymized data summarizing high-level values about your cloud are sent bak to the dragondrop API from managed cloud-concierge containers. These methods can all be seen in the cloud-concierge OSS source code [here](https://github.com/dragondrop-cloud/cloud-concierge/blob/dev/main/internal/implementations/dragon\_drop/http\_dragondrop\_managed\_execution.go) and [here](https://github.com/dragondrop-cloud/cloud-concierge/blob/dev/main/internal/implementations/dragon\_drop/http\_dragondrop\_managed\_visualization.go).

### Can dragondrop engineers access the managed containers once deployed in my cloud?

No. We have no access to the hosted container in your environment (this can be verified by viewing the configuration of the [Open Source Terraform Modules](https://registry.terraform.io/namespaces/dragondrop-cloud) used to host our container in your cloud).

### Can I validate environment variable formats outside of the executable container?

Yes. Our web application includes a client-side variable format validator to help you quickly ensure that your environment variables are appropriately formatted prior to kicking off a Job.
