---
draft: true
title: "Back to Basics: Network Troubleshooting"
description: Accusing someone’s system of being the root cause of a problem can have the
  same effect as calling their baby ugly.
summary: When things go wrong
# summary: Accusing someone’s system of being the root cause of a problem can have the
#   same effect as calling their baby ugly.
date: 2019-10-15T13:11:26-06:00
categories:
  - Series
tags:
  - BacktoBasics
  - TroubleShooting
---
---
{{< lead >}}
When things go wrong
{{< /lead >}}

This post on Network Troubleshooting is the fifth in my Back to Basics series. The first four posts covered [Gathering Requirements]({{< relref "back-to-basics-gathering-requirements" >}}), [Network Design]({{< relref "back-to-basics-design-fundamentals" >}}), and [Network Implementation]({{< relref "back-to-basics-network-implementation" >}}), and [Network Operations]({{< relref "back-to-basics-network-operations" >}}).

Troubleshooting a problem is a great time to remember that the network is at the bottom of the Information Technology stack. This does not mean the network should be viewed as less important than other components in the stack. Quite the contrary, being at the bottom means it is the foundation for everything. The network is also uniquely positioned to view a problem from end to end.

## How May I Be of Service?

When problems arise, it is second nature for people to seek quick exoneration for their systems. This behaviour is true of application developers, database administrators, and systems administrators as much as it is of storage and network administrators. Accusing someone’s system of being the root cause of a problem can have the same effect as calling their baby ugly. Curt communications may be the best you can hope for.

The do-more-with-less culture, pervasive in today’s world, means the same human resources used to keep the lights on are also used to develop and implement new features. Lowering Mean Time to Innocence (MTTI) leaves more time to work on enhancements and change requests that move the business forward. The difficulty with proving innocence is that problems get passed between teams like a hot potato, and the root cause is often not discovered. This behaviour leads to repeating issues and less time to help the business.

All this to say that when your skills are called upon to troubleshoot a problem, do it to the best of your ability. When the network is blamed for a problem rather than being politely asked to check whether it can help fix it, focus on supporting and being of service. Don’t focus on the blame. Rather than assuming the network is innocent, exhaust your troubleshooting steps until the root cause is identified within the system. It will take time, but this level of effort and caring will build trust and credibility.

## Planning the Attack

You should always ask these two questions when confronted with a problem for the first time:

1. Did the system ever work?
2. Did anything change?

The answers to these questions will help target the attack.

It is crucial to have a repeatable, adaptable troubleshooting methodology when attacking complex problems. The following are just a few examples of dozens documented across many industries.

**The OODA Loop:** Observe, Orient, Decide, Act was developed by Colonel John Boyd of the United States Air Force.

**PDCA:** Plan, Do, Check, Act is a management methodology developed by Toyota to support its lean manufacturing process.

**GTD:** Capture, Clarify, Organize, Reflect, Engage are the fundamentals of David Allen’s Getting Things Done productivity methodology.

While these examples are not specific to troubleshooting, they are simple and have common elements that allow for easy iteration. These elements can be summarized into the following rudimentary steps:

- Observe and document symptoms
- Develop a theory on where the likely root cause is or where better observations can be made
- Decide on the best course of action
- Act
- Rinse and repeat until the problem is fixed.

## Divide and Conquer

In this Network Operations post, I discussed the importance of network visibility tools. Troubleshooting problems is where these tools can shine. If network visibility had been built in from day one, the tools might have already captured the symptoms, allowing for immediate analysis. If not, collecting and analyzing evidence may have to wait until the problem occurs again. Waiting for tools to be installed and configured can extend problem resolution for intermittent issues.

Looking at the figures below, it should be clear that having multiple observation points in the network makes it easier to pinpoint the problem. *Figure 1* has a single observation point. Depending on the symptoms, it may be hard to tell if the problem is to the right or to the left of this point. *Figure 2* displays two observation points. Depending on the symptoms, it should be easier to tell if the problem is to the right of both points, to the left of both points, or somewhere in between. Adding more observation points shrinks the search area more quickly.

{{< figure
  src="single-observation-point.png"
  alt="Single Observation Point"
  caption="Figure 1: Single Observation Point"
  >}}

{{< figure
  src="dual-observation-points.png"
  alt="Dual Observation Points"
  caption="Figure 2: Dual Observation Points"
  >}}

## We’re All in this Together

The goal of Information Technology is to help make the business the best it can be. When problems occur in systems that support the business, all divisions of Information Technology need to step up and be part of the solution. For many reasons, this doesn’t always happen. In any situation, we can only control ourselves. Individual positivity, responsiveness, openness, and a sense of service go a long way toward building credibility, trust, and a high-performing team.

The final post in this Back to Basics series discusses [the network lifecycle]({{< relref "back-to-basics-the-network-lifecycle" >}}).

---
