# DevOps
- Dev is measured by delivering features, which means deploying changes
- Ops is measured by uptime, but changes are bad for stability

## Timeline
- 2007: **Patrick Debois**
- 2008: **Patrick Debois** and **Andrew Shafer**
- 2009: **John Allspaw** and **Paul Hammond**
- 2009 : **Patrick** first **DevOpsDays**

## Goals
- Fast **time-to-market(TTM)**
- Few production failures
- Immediate recovery from failures

## Downsides of Traditional Silos
- "Black boxed" lead to finger pointing
- Lengthy process means slow time-to-market
- Lack of automation means things like builds and deployments are inconsistent
- It takes a long time to identify and fix problems

## Build Automation
- fast
- consistent
- repeatable
- portable
- reliable

## Continuous Integration
Continously merging code into a single branch or mainline

Continuous integration is usually done with the help of a **CI server**

When a developer commits a code change, the **CI server** sees the change and automatically performs a build, also executing automated tests.

**Early detection** of certain types of bugs

**Eliminate the scramble** to integrate just tbefore a big release

[Jenkins](/jenkins.md)



## Continuous Delivery and Continuous Deployment
**Continuous Delivery (CD)** is keeping the code in a deployalbe state. **Continuous Deployment** is actually doing the deployment frequently. 

## Infrastructure as Code
**Infrastructure as Code(IaC)**

## Configuration Management
**Configuration Management**: maintainng and changing the state of pieces of infrastructure in a consistent, maintainable, and stable way

Configuration management allows you to minimize **configuration drift**

## Orchestration
Orchestration: automation that supports processes and workflows, such as provisioning resources

- Scalability 
- Stability
- Save time
- Self-service

https://xebialabs.com/periodic-table-of-devops-tools/



