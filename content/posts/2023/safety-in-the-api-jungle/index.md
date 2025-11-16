---
draft: false
title: Safety in the API Jungle
description: It's a jungle out there and predators are homing in on the smell of fresh
  attack vectors and security vulnerabilities exposed by APIs.
summary: APIs are a new attack surface. A hidden attack surface.
# summary: It's a jungle out there and predators are homing in on the smell of fresh
#   attack vectors and security vulnerabilities exposed by APIs.
date: 2023-07-15T07:36:00-06:00
categories:
  - Events
tags:
  - Security Field Day
  - Tech Field Day
  - TFD
  - XFD
---
---
{{< lead >}}
APIs are a new attack surface. A hidden attack surface.
{{< /lead >}}

Application Programming Interfaces (API) power the modern world. They can be found in applications that control lighting, garage door openers, and security systems. They are used to check the weather, map travel routes, and book flights. APIs are leveraged to access personal information, transfer money, and control nuclear reactors. Mission-critical operations, digital transformation, and information availability all rely on them - APIs are everywhere.

It's a jungle out there and predators are homing in on the smell of fresh attack vectors and security vulnerabilities exposed by APIs. [Noname Security](https://techfieldday.com/companies/noname-security/) has a solution to this security problem, which they presented at [Security Field Day 9 (XFD9)](https://techfieldday.com/event/xfd9/).

## Exposure

The attack surface exposed by APIs presents a few challenges for security. First, they're easy to exploit because they're externally accessible. Second, APIs are reported to be growing more than 200% per year.[^report] Akamai revealed that 83% of traffic on their secure content delivery network is related to APIs while CloudFlare reported API traffic accounted for 54% of the total measured traffic. Third, API management is difficult. They can be orphaned if old systems aren't decommissioned - which is common in the cloud. Continuous development leads to continuous abandonment - zombie APIs - which still grant access to data. Old versions of APIs don't get decommissioned because developers don't want to introduce backward incompatibilities.

[^report]: 2022 API Security Trends Report, 451 Research; 2022 State of the API Report, Postman; API Security Disconnect, 2022

Because most APIs are HTTP-based, securing them has traditionally been left to the duo of Web Application Firewalls (WAF) and API gateways. A WAF passes traffic if it looks valid, however, it's difficult to differentiate between normal and malicious HTTP traffic. Also, most abuses don't happen at this level, they happen at the authorization and business logic levels. Bad traffic manipulates API logic that gives access to data or the application.

## Gimme Shelter

[Noname Security](https://nonamesecurity.com/) was founded on the thesis that APIs would become the most frequent attack vector and that current security solutions would not be able to provide sufficient protection. Their platform is built upon four pillars.

### Discovery

Subscribing to the axiom `you can't protect what you can't see`, discovery is all about API inventory. Providing security for *most* of your APIs simply isn't good enough. An attacker only needs to be right once or be lucky once to gain access to your data. Two broad methods - traffic mirroring and integrations - are employed to gain a complete API census.

For traffic mirroring, WAFs and load balancers can send copies of decrypted traffic to Noname. Another method is to grab copies of traffic right off the network, decrypt them with a packet broker (i.e., [Gigamon](https://techfieldday.com/companies/gigamon/)), then forward them to Noname.

Examples of integrations are the plugins Noname has developed for popular API gateways and the hooks into the development process.

### Posture

Posture looks for vulnerabilities and misconfigurations by determining:

- What kind of data is transferred
- If that meets regulatory compliance
- If it's facing the Internet when it should only be internal
- How authentication and authorization are configured

Noname then builds a graph that lets the team visualize all the communication, making it easier to see if anything needs to be changed.

### Runtime

Traffic collection isn't only useful for discovery. Runtime is constantly profiling real-time API traffic to detect deviations from normal. Behavioural analytics and Machine Learning create models to tell the difference between good and bad traffic.

### Testing

Detecting and removing vulnerabilities before they make it to production reduces impact, cost, and response time. Noname's system integrates with your CI/CD pipeline to provide full [Dynamic Application Security Testing (DAST)](https://en.wikipedia.org/wiki/Dynamic_application_security_testing) coverage of every API you develop. This testing allows API developers to adopt a widely accepted development process known as [Shift Left](https://en.wikipedia.org/wiki/Shift-left_testing). These methods not only reduce the number of vulnerabilities that make it to production, but allow for code modifications earlier in the development process when there is less code to change.

## Security is Always a Team Effort

Noname's solution for API security augments the traditional approach rather than replacing it. On the front end, your WAFs and API gateways are still needed and become more useful as they feed valuable information to Noname. In the middle, the traffic collected by your Network Visibility Fabric has a new use case. Noname's platform doesn't provide enforcement. Rather, it integrates with back-end systems you probably already have deployed. Your existing investments in SIEM, SOAR, and ITSM products are configured to react appropriately to information they receive from Noname.

## Grab Some Jungle Food and Watch Noname's Presentations and Demos

{{< youtube id="7FlTOnXqKEM" title="Noname Security Overview with Filip Verloy" >}}

{{< youtube id="4GfRwBSk2d8" title="Noname Security Platform Overview and Live Demo" >}}

{{< youtube id="nGEQYzQHM9I" title="Noname Security Active Testing Overview and Live Demo" >}}

---
> **Disclosure:** I was invited to participate in XFD9, and this participation is voluntary. While Gestalt IT hosts the event, I am not required to produce this post. It was not reviewed or edited by Gestalt IT or the sponsors of the event.

---
