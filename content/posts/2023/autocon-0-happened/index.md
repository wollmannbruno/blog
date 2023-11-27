---
draft: false
title: AutoCon 0 Happened
description: 
lead: It Was Amazing.
summary: 
date: 2023-11-18T09:06:08-06:00
thumbnail: images/autocon-0-happened.jpg
images:
  - images/autocon-0-happened.jpg
categories:
  - Events
tags:
  - Network Automation
  - AutoCon
  - NAF
---
---
The [Network Automation Forum](https://networkautomation.forum) recently hosted the inaugural AutoCon conference, AutoCon 0[^0-based], in Denver, Colorado, to answer **"WHY HAVEN’T WE SEEN FULL ADOPTION OF NETWORK AUTOMATION, YET?"** The question shows optimism for the future of network automation, one of the conference's main themes, and the attitude held by its 300-ish attendees.

[^0-based]: Gotta love the 0-based indexing.

For two days, the conference featured two keynotes, a few presentations to showcase inspirational success stories, panel discussions centered on specific topics, and perspectives from a few vendors. It ended with a working session titled **"Now What?"**. Audience participation had been present for all sessions, but this one focused on the audience; it was an open-mic night.

## What Happened

### Keynotes

[John Willis](https://www.linkedin.com/in/johnwillisatlanta/) opened the conference by discussing his experience at the beginning of the DevOps movement, which he helped create. His talk centered on the journey and included successes and failures as software developers and sysadmins collaborated to create better experiences for their customers and the businesses they served. John wanted to convey that networking is not special, so there is no good reason to lag so far behind other disciplines in adopting automation.

[Kireeti Kompella](https://www.linkedin.com/in/kireetikompella/) provided some big-picture thinking for network automation by using examples of the advancements made in the automobile industry. Cars have progressed from 100% operator-controlled to self-driving in limited use cases. Between these two states, there are examples of automation that are very useful with varying degrees of operator control. Cruise control, adaptive cruise control, and lane assist are a few examples. If the networking industry works towards creating self-driving networks[^sdn], whether we get there or not, there will be many benefits by simply embarking on the journey.

[^sdn]: The other SDN.

### Presentations

The presentations offered hope and inspiration by sharing network automation success stories.

Topics included:

- Read-only automation to simplify and accelerate troubleshooting
- Automated deployments across various network types
- Orchestrating with system deployments
- Integrating observability and monitoring tools
- Automation architectures
- Getting started and how to progress
- Automating service assurance and the network design process

### Panel Discussions

Panels consisted of automation experts led by a moderator. Some panels started with brief presentations, but all consisted of moderator-asked questions and questions from the audience.

Topic included:

- The current state of network automation
- Challenges to adoption
- The role of AI/ML
- Observability
- Lessons from public cloud
- How can we do better

## What Needs To Happen

Here are some items that stood out for me during the conference.

### Common Ground

Network automation lacks a clear taxonomy for definitions. What are DevOps, NetDevOps, automation, orchestration, visibility, and observability? At the conference, there was some debate about what each means, how they differ, and where they overlap. Network automation will seem nebulous to the uninitiated until those at the forefront can agree on definitions and clearly articulate their meaning.

Some presenters shared high-level automation architectures; although they had some commonalities, there were also differences. These variations mean that once you progress beyond the most basic automation practices, your architecture is probably a snowflake[^snowflake] and will continue to diverge from all others. Pairing a common lexicon with some reference automation architectures would help lower the barrier to network automation.

[^snowflake]: This may or may not describe the network you're attempting to automate.

Conversations that center on definitions and architectures invariably lead to debates about standards. Our industry might be able to agree on definitions and high-level architectures, but standards for data models and APIs may not be attainable or even desirable. You only have to look as far as SNMP to see an example of a standard that morphed to accommodate every possible vendor use case. YANG is suffering a similar fate. Vendors also need to innovate and differentiate themselves from their competitors, which requires standards to be flexible or risk abandonment.

### Build vs Buy

Most of the automation on display was of the DIY variety. Some architectures had a sprinkling of COTS solutions, but open-source and home-grown applications perform the heavy lifting.

### Always Be Selling

### TDD

### How Do You Handle The Truth

## What Happens Next

![My AutoCon0 Badge](autocon0-badge.jpg)
