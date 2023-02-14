---
description: Best practices for using dragondrop Jobs to cover your cloud
---

# How Many Jobs Should We Use?

### Recommended Job Segmentations

We recommend creating one Job per logical grouping of infrastructure. This allows dragondrop recommendations for different infrastructure groupings to be assigned to relevant engineers with expertise in that particular grouping, and keeps recommendations relevant and focused for those reviewing them.

Some examples of infrastructure groupings for assigning dragondrop jobs:

* Infrastructure segmented by application.
* Infrastructure segmented by managing team.
* Infrastructure segmented by Cloud Provider
* Infrastructure segmented by development environment (dev, prod, staging)

### Hard Restrictions

The only hard restriction is that a single dragondrop job can only output recommendations and results to a single repository in your version control system.

### No Restrictions

* An unlimited number of users for your dragondrop organization.
* A Job can be run an unlimited number of times each month.
