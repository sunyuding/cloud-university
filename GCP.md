# GCP
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
