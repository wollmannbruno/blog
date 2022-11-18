---
draft: false
title: The What and How of Pica8
description: Pica8 presented at Networking Field Day 28 to display why their system
  could be viable for keeping corporate initiatives and supporting IT projects on track.
lead: Simple and flexible
summary: Pica8 presented at Networking Field Day 28 to display why their system
  could be viable for keeping corporate initiatives and supporting IT projects on track.
date: 2022-06-04T10:20:25-06:00
thumbnail: /images/the-what-and-how-of-pica8.jpg
images:
  - /images/the-what-and-how-of-pica8.jpg
categories:
  - Events
tags:
  - Networking Field Day
  - NFD
  - Tech Field Day
  - TFD
---
---
Supply chain issues, mainly caused by the Covid-19 pandemic, have increased delivery times of some network gear to a level where organizations are exploring options away from their traditional vendors. Not wanting to let a crisis go to waste, Pica8 presented at [Networking Field Day 28](https://techfieldday.com/event/nfd28/) to display why their system could be viable for keeping corporate initiatives and supporting IT projects on track.

Here are a couple of points that resonated with me during NFD28.

## What can you do?

{{< tweet user="802Tophat" id="1527456550545248265" >}}

Who likes dealing with licensing? My friend [Richard McIntosh](https://802tophat.wordpress.com) does not. Read some of the replies to his tweet, and you will see that most people find licensing schemes to be painful. When you have to run a separate licensing and compliance server in your environment, it is a good indication that the balance between value and complexity is not weighted in the customer's favour. To be fair to Cisco, they are not the only vendor where licensing is a nightmare - which is usually the result of companies chasing recurring revenues through subscription and feature-based licensing.

Enter the Pica8 single license model. A single license per device provides access to all features for all use cases in any place in the network.

**With this flexibility, you can:**

- buy a license once, run it anywhere, and swap it to any hardware forever,
- use a license on any device no matter the number or speed of the ports,
- enable any feature on a licensed device,
- combined with yearly support, upgrade a licensed device.

Pica8 has made life simple when purchasing what you need, repurposing gear, and enabling/disabling features.

## How can you do it?

Pica8's solution consists of two components. First is the AmpCon network controller, the automation command centre for your enterprise network. Second is the PicOS switch software, which turns your white box into an enterprise switch, automated by AmpCon.

This dynamic duo was on full display during the [presentation](https://techfieldday.com/appearance/pica8-presents-at-networking-field-day-28/). The first demo included an automated deployment of Network Access Control (NAC) (Zero-Trust networking if you like buzz-words). In contrast, the second demo featured pushing EVPN-VXLAN configurations to a group of switches. Both NAC and EVPN-VXLAN have fairly complex configurations that contain many variables and options. Rather than focusing on the configurations themselves, I want to highlight how the combination of AmpCon and PicOS made short work of these deployments.

**Ansible:** Ansible is currently the lead horse on the global, open-source network automation track and is integrated into AmpCon to set up and maintain your network environment. In addition to the out-of-the-box setup of Ansible, you can create customized workflows by adding your playbooks to the system.

**Jinja2:** Ansible uses the Jinja2 templating language, so Pica8 has also integrated Jinja2 into AmpCon. However, rather than being limited to standard, text-based Jinja, Pica8 has made all PicOS configuration items available as point-and-click options in the AmpCon UI. Taking it one step further, you can transform each template into a wizard so junior network engineers can fill in a few variables to create complex, standardized configurations.

**REST API:** A GUI is good for some tasks, but it is usually cumbersome and error-prone when large amounts of information have to be typed in by a human. The REST API allows your team to store everything as code, where development practices can be created and automated, providing better outcomes. Variables are then entered programmatically after first running through a validation gauntlet (everyone performs input validation, right?).

**Built for Automation:** Automation can be a game-changer and is the natural evolution of many manual network configuration, maintenance, and troubleshooting scenarios. Automation can also be scary from a risk perspective because the blast radius of a mistake grows from a single device without automation to multiple when using a centralized controller. PicOS helps remove some of this risk by being fully transactional and supporting a commit and rollback model; a la JUNOS.

## What do you need?

Of course, PicOS needs to run on switches. The [Hardware Compatibility](https://www.pica8.com/resources/?resourcelib_category=hardware-compatibility/) list features a selection of Dell, Delta, and Edge-Core hardware. PicOS features and configuration guides are available on Pica8’s [documentation site](https://docs.pica8.com/). Want to try it before you buy it? Spin up [PicOS-V](https://www.pica8.com/picos-v/) in your virtual lab to see it in action.

An architect needs to consider many factors when designing a network. Decisions can be harder to make when needing or wanting to change your incumbent networking solution. With solutions for campus, DC, branch, and IoT networking, the timing might be perfect for Pica8 to capitalize on its mission of being the open networking alternative to Cisco and Juniper. More importantly, their solutions may also fit perfectly into your strategic IT plans.

---
> **Disclosure:**  Gestalt IT hosted NFD28 and invited me to participate, which I did voluntarily. Gestalt IT paid for my transportation, accommodations, food, and beverage for the duration of the event. I am not required to produce this post, and it was not reviewed or edited by Gestalt IT or the sponsors of the event.

---
