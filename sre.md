# Site Reliability Engineeing
If you know about SRE and DevOps best practices and already use SLOs to measure the reliability of your services, you may find this material covers familiar ground. We talk about SRE as Google's implementation of DevOps philosophy, why Google's Customer Reliability Engineering team came to exist and the value proposition of SLO's to various parts of our organization. Your development product and operations teams can all benefit from understanding and applying SRE principles. The first module, measuring and targeting reliability, sets out why a service should aim to be just reliable enough to meet the expectations of its users and to keep them happy. It then shows how quantifiable metrics of service reliability and user happiness can be used to define a measurable target that is reliable enough. The second module operating for reliability, explains how setting a target for reliability yields a budget for unreliability. It demonstrates the utility of an error budget for both short and long-term decision-making and covers some of the things that operations can do to make a service more reliable. The third module, choosing a good SLI, goes into detail about what kind of monitoring metrics make good service level indicators and the pros and cons of different measurement strategies. It describes common types of SLI specifications, the recommended way of structuring an SLI specification and ways to reduce the number and complexity of fine-grained SLIs to more manageable levels. Finally, it talks about ways to set an initial SLO target for a newly developed SLI. The fourth module developing SLOs and SLIs, walks you through the four-step process we use to develop a set of SLIs and SLOs for a simple user journey of a fictional mobile game service. It talks in detail about refining an SLI specification into an implementation by choosing appropriate measurement methods, thresholds, and success criteria. The fifth module, Quantifying Risks to your SLO, introduces the CRE risk analysis spreadsheet and demonstrates how to use it to estimate your risk to your newly developed SLOs. This exercise can be especially useful when prioritizing long-term reliability work. The sixth and final module, Consequences of SLO Misses, explains why documenting both your SLOs and the responsibilities of your different stakeholders in your organization when those SLOs are missed is essential. It gives advice on what to document, and how to create an error budget policy that incentivizes all parties to engineer for service reliability while minimizing potential organizational friction. Next, we're going to talk about DevOps in SRE and the differences and similarities between the two groups. Feel free to skip to module one if you're already familiar with this material, but if you're new to this or you feel like you need a refresher, continue on.

[What's the Difference Between DevOps and SRE?](https://youtu.be/uTEL8Ff1Zvk)

| DevOps                    | SRE | 
|---------------------------|-----------------|
| Reduce Organization Silos | Share ownership | 
| Accept Failure as Normal  | SLOs & Blameless PMs | 
| Implement Gradual Change  | Reduce costs of failure | 
| Leverage Tooling & Automation | Automate this year's job away  |
| Measure Everything        | Measure toil and reliability | 


```bash
class SRE implements DevOps
```

[Now SRE Everyone Else with CRE!](https://youtu.be/GQPzaq-owYM)

## Three Reliability Principles
1. Reliability is the most important featrue.
2. Users, not monitoring, decide reliability.
3. Well-engineered..
    software = 99.9%
    operations = 99.99%
    business = 99.999%

## Reliability in the Cloud
- 28-day error budget 99.9% = 40 min
- 28-day error budget 99.99% = 4 min
- 28-day error budget 99.999%  = 24 sec

## SLO: Service Level Objective
SLOs are internal promises to meet customer expectations.

Question: If reliability is a feature, when do you prioritize it versus otehr features?

Common language and understanding around **reliability**.

The problem with building new features quickly is that there's often a strong negative correlation between development velocity and system reliability.

Question: What is the right level of reliability for the system you support?

- meets target SLO => happy customers
- misses target SLO => sad customers

There are many edge cases with SLOs that you should be aware of and you might want to set one or more targets to cover these edge cases. For example, it's common to set one latency target for the median user and one for the long tail.

## SLA: Service Level Agreements
SLAs are external promises to customers and must come with consequences.

SLOs should be stronger than your SLAs to catch issues before they violate customer expectation.

Question: A startup just suffered a major outage and wants to change its ways. What are some possible ways it can reduce risks to its service? Select all that apply.
- Slowing down the rate of change to the system
- Focus on automation effors
- Doing fewer pushes

SLAs must have a consequence if violated.

## Targeting Reliability


## Operating for Reliability


## Choosing a Good SLI


## Developing SLOs and SLIs


## Quantifying Risks to SLOs


## Consequences of SLO Misses


- [ ] [SRE](https://www.coursera.org/learn/site-reliability-engineering-slos)