# GCP
Seven categories of GCP services:

- Compute: houses a variety of machine types that support any type of workload. The different computing options let you decide how involved you want to be with operational details and infrastructure amongst other things.
- Storage: data storage and database options for structured or unstructured, relational or non relational data.
- Networking: services that balance application traffic and provision security rules amongst other things.
- Stackdriver: a suite of cross-cloud logging, monitoring, trace, and other service reliability tools.
- Tools: services for developers managing deployments and application build pipelines.
- Big Data: services that allow you to process and analyze large datasets.
- Artificial Intelligence: a suite of APIs that run specific artificial intelligence and machine learning tasks on the Google Cloud platform.

Primitive roles set project-level permissions and unless otherwise specified, they control access and management to all GCP services.

## Technical papers on the Google Infrastructure
- [ ] GFS (Google File System)
- [ ] BigTable
- [ ] MapReduce

## Google Compute Engine [IaaS]

## Google App Engine [PaaS]
- What are the two app engine environments
    - Standard
    - Flexible
- What the standard environment offers
    - A simpler deployment experience, fine grained auto-scaling and a free daily usage quota.
    - At low utilization, some app could run at no cost.
- What are the runtime environments provided by app engine
    - Specific versions of JAVA, Python, PHP and Go
- What are the restrictions on the standard environment
    - The code is runned inside a sand-box, that means the code runs independently of software or hardware
    - The app can't write to local file system
    - All requests have a 60s timeout
    - Can't install arbitrary third party software
- Why choose flexible environment
    - When the restrictions in the standard environment do not match the requisites of the app
- What is the flexible environment
    - Instead of a code, the app engine lets the user choose a container to run
- What's the difference between flexible environment and kubernetes
    - App engine treats containers as a means to an end, and kubernetes containers are fundamental organizing principle
