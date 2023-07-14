---
draft: true
title: Safety in the API Jungle
description: It's a jungle out there and predators are homing in on the smell of fresh
  attack vectors and security vulnerabilities exposed by APIs.
lead: 
summary: It's a jungle out there and predators are homing in on the smell of fresh
  attack vectors and security vulnerabilities exposed by APIs.
date: 2023-07-08T09:16:40-06:00
thumbnail: images/safety-in-the-api-jungle.jpg
images:
  - images/safety-in-the-api-jungle.jpg
categories:
  - Events
tags:
  - Security Field Day
  - Tech Field Day
  - TFD
  - XFD
---
---
Application Programming Interfaces (API) power the modern world. They can be found in applications that control lighting, garage door openers, and security systems. They are used to check the weather, map travel routes, and book flights. APIs are leveraged to access personal information, transfer money, and control nuclear reactors. Mission-critical operations, digital transformation, and information availability all rely on them - APIs are everywhere.

It's a jungle out there and predators are homing in on the smell of fresh attack vectors and security vulnerabilities exposed by APIs. [Noname Security](https://techfieldday.com/companies/noname-security/) has a solution to this security problem, which they presented at [Security Field Day 9 (XFD9)](https://techfieldday.com/event/xfd9/).

## Exposure

The attack surface exposed by APIs presents a few challenges for security. First, they're easy to exploit because they're externally accessible. Second, APIs are reported to be growing more than 200% per year. Akamai revealed that 83% of traffic on their secure content delivery network is related to APIs while CloudFlare reported API traffic accounted for 54% of the total measured traffic. Third, API management is difficult. They can be orphaned if old systems aren't decommissioned - which is common in the cloud. Continuous development leads to continuous abandonment - zombie APIs - which still grant access to data. Old versions of APIs don't get decommissioned because developers don't want to introduce backward incompatibilities.

Because most APIs are HTTP-based, securing them has traditionally been left to the duo of Web Application Firewalls (WAF) and API gateways. A WAF passes traffic if it looks valid, however, it's difficult to differentiate between normal and malicious HTTP traffic. Also, most abuses don't happen at this level, they happen at the authorization and business logic levels. Bad traffic manipulates API logic that gives access to data or the application.

## Gimme Shelter

As we'll see in this section, [Noname Security's](https://nonamesecurity.com/) solution for API security augments the traditional approach rather than replacing it. Their platform is built upon four pillars.

### Discovery

Subscribing to the axiom `you can't protect what you can't see`, discovery is all about API inventory. Providing security for *most* of your APIs simply isn't good enough. An attacker only needs to be right once or be lucky once to gain access to your data. Two broad methods - traffic mirroring and integrations - are employed to gain a complete API census.


### Posture


### Runtime


### Testing


## Watch the Presentations

{{< youtube 7FlTOnXqKEM >}}

{{< youtube 4GfRwBSk2d8 >}}

{{< youtube nGEQYzQHM9I >}}

---
> **Disclosure:** I was invited to participate in XFD9, and this participation is voluntary. While Gestalt IT hosts the event, I am not required to produce this post. It was not reviewed or edited by Gestalt IT or the sponsors of the event.

---
