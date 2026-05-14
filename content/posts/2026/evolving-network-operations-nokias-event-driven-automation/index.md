---
draft: false
title: Evolving Network Operations Nokias Event Driven Automation
description: Nokia's event-driven automation enables networks to self-adjust in
  real-time, responding to various events without manual intervention.
summary: Nokia's event-driven automation is transforming network operations.
externalUrl: https://www.linkedin.com/pulse/evolving-network-operations-nokias-event-driven-bruno-wollmann-oprvc/?trackingId=LTMnSDbMRD6W5pu%2BraXmlg%3D%3D
date: 2024-11-24T21:42:19-06:00
categories:
  - Events
tags:
  - NFDxNokia
  - Tech Field Day
  - TFDx
---
---
{{< lead >}}
Nokia's event-driven automation is transforming network operations
{{< /lead >}}

[Nokia](https://www.linkedin.com/company/nokia/) is well-known for developing high-quality, innovative solutions. For the last two years, one of its teams has focused on a product to revive data centre (DC) network operations. This effort resulted in Event-Driven Automation (EDA), an innovative product that removes network fragility. Nokia introduced EDA to the [Tech Field Day](https://techfieldday.com) crowd at [Networking Field Day Exclusive with Nokia](https://techfieldday.com/event/nfdxnokia24/).

## OPPORTUNITY

> **If we built airplanes like we build networks, I would walk everywhere and always be looking up for falling airplanes.** -- *[Michael Bushong](https://www.linkedin.com/in/michaelbushong/)*

The ugly truth in the networking industry is that networks work best when left alone. This is because two-thirds of network outages are caused by human error. For confirmation, one need only look at the restrictive change windows implemented in most organizations. These windows limit network changes to times with the least potential impact on the business and are only approved after running the Change Advisory Board (CAB) gauntlet multiple times.

- If your change windows avoid fiscal year-ends, your network may be fragile.
- If your change windows avoid major holidays, your network may be fragile.
- If your change windows avoid full moons, your network may be fragile.
- If you observe "read-only Fridays," your network may be fragile.

When considering this problem space, Nokia asked, "What is the proper problem to solve?" Their answer was, "Solve the safety issue."

## THEORY

> **We have enough protocols; we should be working on operations stuff.** - *[Vach Kompella](https://www.linkedin.com/in/vachkompella/)*

Nokia asserts that networking is a program. It is something you create, edit, run, debug, and expect to achieve specific outcomes. Like any application, the network has inputs, outputs, and behaviours. While software development practices have evolved, network operations have mostly stagnated.

Software development started using basic text editors to manipulate low-level assembly languages. Integrated Development Environments (IDEs) combined with high-level languages are now commonplace. This evolution has arguably improved software quality and made it easier to become a developer.

The pace of network operations' evolution can best be described as glacial. Most modern networks are managed like their predecessors: device-by-device through the CLI. The CLI is the network's assembly language; it is low-level and lacks abstractions. This means that the incantations used to configure a networking device are specific to that vendor and often specific to that model within the vendor's fleet. This specificity has also made it harder to become a well-rounded network engineer and has given rise to many four and five-letter vendor-specific certifications.

Network automation has existed for many years, promising to evolve network operations and address the human error problem. However, most organizations either do not have a network automation practice or use automation to deliver faster, but not necessarily safer, changes.

Nokia's focus on network operations has resulted in a solution that provides quick evolution for teams looking to improve safety and reliability. EDA combines Intent-Based Networking (IBN) with software development principles to create an IDE for the network.

IBN provides models for networking concepts, allowing practitioners to define services using high-level abstractions rather than device CLI. This service definition, or intent, is entered and stored in a repository, often called a Source of Truth (SoT), before application to individual nodes. The SoT provides safety as the design proceeds through reviews and approvals before testing, final acceptance, and implementation. It is only in the testing and implementation stages that high-level concepts are converted to low-level configurations. Until then, the hardware's make and model do not matter.

## PRACTICE

> **Speed is good; reliability is better.** -- *[Wim Henderickx](https://www.linkedin.com/in/wim-henderickx-393b3a/)*

EDA's foundation is Kubernetes. While most network operations personnel may ignore this fact, as most will never need to interact with it, it does reveal Nokia's key design philosophies: reliability, flexibility, and extensibility. These philosophies were displayed during a series of demos and some lab work.

The day-0 portion of the demo onboarded several data centre fabric devices through Zero-Touch Provisioning (ZTP). EDA then deployed the fabric config to these devices based on the stored intent. By the end of the day, we had made several configuration changes, upgraded a few devices, and onboarded additional nodes. We accomplished all this by declaring our intent in EDA's SoT, committing it, and then letting EDA calculate and deploy the specific device configuration. Pre and post-checks ensured all changes were atomic, providing automatic rollbacks and a return to the previous state in case of errors.

The power of EDA's version control system, backed by Git, became apparent when the final task rolled back the network to the initial commit. Not only was the original configuration restored, but all network devices were downgraded to their committed version. This giant "undo" button, combined with network-wide atomic changes, adds a level of safety largely unattainable with current CLI-based operations.

Integrating a digital twin of your network with EDA ensures that all changes are tested before being deployed to production. This feature is vital when minimizing the effects of disruptive changes.

Operating a network involves more than just deploying configuration. It also involves ensuring that the network is running as intended. The word "event-driven" in the name suggests that EDA is a total solution.

EDA modernizes network monitoring by ingesting the rich telemetry streamed from most DC hardware rather than using periodic polling. This allows EDA to respond to events in real time while avoiding unnecessary work.

EDA exposes all data it collects through the EDA Query Language (EQL), loosely based on Jira's query language. Natural language queries are made possible through EDA's use of Open AI. The results of these queries might be for human consumption, or they can feed into additional automation to keep the network in its intended state.

## CONCLUSION

Kubernetes normalized the pod concept, while EDA does the same for all network primitives, making it multi-vendor and multi-domain. Nokia started building EDA in 2022 with ambitious goals, even though every vendor has a controller-based system for their DC gear.

EDA currently supports the Service Router Operating System (SR OS) and the Service Router Linux (SR Linux) operating system. It is actively developing for Software for Open Networking in the Cloud (SONiC) and will start for Arista or Cisco within a year.

To gain traction in the industry, Nokia has opened a store where other developers can contribute modules that extend EDA's functionality. Because EDA is intended to be multi-domain, these modules can expand the system beyond DC fabrics and into server, DPU, GPU, and other types of infrastructure automation.

I welcome EDA to the network automation landscape and hope it can revitalize the evolution of network operations.

---
> **Disclosure:** Gestalt IT hosted NFDxNokia and invited me to participate. I am not required to produce this post, nor was I paid for it. It was not reviewed or edited by Gestalt IT or Nokia.
---
