---
draft: false
title: "Back to Basics: Gathering Requirements"
description: Your mission, should you choose to accept it, is to be the lead network
  architect for a data centre migration project for ACME Corporation.
summary: Mission parameters
# summary: Your mission, should you choose to accept it, is to be the lead network
#   architect for a data centre migration project for ACME Corporation.
date: 2019-08-21T14:32:00-06:00
categories:
  - Series
tags:
  - BacktoBasics
  - Design
---
---
{{< lead >}}
Mission parameters
{{< /lead >}}

Your mission, should you choose to accept it, is to serve as the lead network architect for a data centre migration project at ACME Corporation. ACME is the world leader in manufacturing rocket-powered roller skates, jet-powered bikes, giant rubber bands, giant slingshots, and various types of bombs and dynamite. Two primary drivers are forcing ACME Corporation to move its data centre. First, the current data centre is co-located with their manufacturing and testing facility, and the constant explosions and accidents have compromised stability. Second, due to the successful breeding habits of roadrunners and bunnies, ACME has experienced tremendous growth in recent years. They have projected that they will outgrow their current data centre in the next three years.

Where do you start?

This series of blog posts will break down this daunting project into smaller tasks. We’ll focus on the items to consider in each task to turn this mission from impossible to possible.

## Gathering Requirements

Like many networks, ACME’s exist for one reason: to support the business. The network has been operating admirably for years, and it would be easy to build the new data centre network as a mirror image of the current one. However, this project provides the perfect opportunity to ensure all business and application requirements are met now and into the foreseeable future. The only way to gauge this is to gather requirements.

### Business and Application Requirements

As expected, ACME hosts a variety of administrative, financial and manufacturing applications in its data centre. Discovery meetings with the key stakeholders of each application should reveal when each application is most commonly used, application dependencies, expected uptimes, acceptable outage windows, and the effects of an outage on the business. These meetings should take the form of a conversation, with [active listening](https://www.verywellmind.com/what-is-active-listening-3024343) to uncover any pain points. These pain points should serve as beacons for requirements that need to be met or for ways the current system can be improved.

Translating application requirements to network requirements is always tricky. One reason for this is that applications sit at the top of the information technology (IT) stack while networks sit a few layers below, at the bottom. This gap means the groups speak different languages. Often, it feels like a network architect needs to read minds to complete the translation.

### Legal Requirements

Many industries are subject to legal compliance requirements, which can affect network design. Because ACME sells directly to its customers by accepting credit cards, it must comply with the Payment Card Industry (PCI) standard.

To ensure PCI is interpreted correctly, ACME’s privacy officer, Daffy Duck, should be consulted.

### Technical Requirements

Within the IT stack, servers, storage and middleware are layered between the applications and the network. The groups that manage these layers are also customers of the network and, as such, have their own requirements to be successful in supporting the applications and business. Cooperation with these groups will determine connectivity types, connectivity speeds, reliability, and redundancy requirements.
ACME’s network monitoring systems provide detailed reports of bandwidth and traffic patterns. This information will help ensure that the network is sized appropriately for the projected growth.

### Security Requirements

It goes without saying that security should be included from the outset. An insecure network puts the business, and many livelihoods, at risk. Striking a balance between usability and security is difficult, as new attacks are invented every day. There are always tradeoffs when balancing usability and security.

ACME’s Chief Information Security Officer (CISO), Yosemite Sam, is a shoot-first, ask-questions-later type. He would like to see systems locked down as tightly as possible, no matter what. It’s essential to have a conversation with him to soften this stance, as it’s not very user-friendly. What level of risk is Mr. Sam willing to accept on behalf of ACME Corporation to achieve balance?

### Documentation

All requirements should be gathered in a document and categorized by type. Classifying each one as either mandatory or optional is also beneficial. Once created, this document needs to be approved and signed by all stakeholders. Signatures should in no way imply that requirements gathering is complete. Instead, requirements gathering should be an iterative process. You will undoubtedly have more questions that clarify some requirements, remove requirements or expose new ones. Being iterative also allows stakeholders to ask questions and provide more information, all with the intent of fine-tuning the living requirements document.

Constraints can be just as crucial as requirements and can be found in any of the above categories. Requirements typically consist of the functionality a system must have. Constraints normally include limitations imposed on a system. As every project is usually tied to a budget, there will most certainly be a financial constraint.

## Conclusion

Requirements gathering is hard work. Change can be scary, and inaccurate requirements can be the result. Active listening during open conversations builds trust, helping alleviate the fear of change.

It’s exciting to build a new network. It’s even more exciting when that network contributes to the business's success. Requirements gathering isn’t glamorous by any means, but it is an important task to perform to the best of your abilities, no matter the size of the network.

Check the next post in this Back to Basics series, where we discuss the [design process]({{< relref "back-to-basics-design-fundamentals" >}}).

---
