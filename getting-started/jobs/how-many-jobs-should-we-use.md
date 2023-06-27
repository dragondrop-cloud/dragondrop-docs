---
description: Best practices for using managed Jobs to cover your cloud
---

# How Many Jobs Should We Use?

### Recommended Job Segmentations

We recommend creating one Job per logical grouping of infrastructure. This allows [cloud-concierge](https://github.com/dragondrop-cloud/cloud-concierge) recommendations for different infrastructure groupings to be assigned to relevant engineers with expertise in that particular grouping, and keeps recommendations relevant and focused for those reviewing them.

Some examples of infrastructure groupings for assigning cloud-concierge jobs:

* Infrastructure segmented by application.
* Infrastructure segmented by managing team.
* Infrastructure segmented by Cloud Provider
* Infrastructure segmented by development environment (dev, prod, staging)

### Hard Restrictions

The only hard restriction is that a single cloud-concierge container can only output recommendations and results to a single repository in your version control system.

### No Restrictions

* A Job can be run an unlimited number of times each month.
