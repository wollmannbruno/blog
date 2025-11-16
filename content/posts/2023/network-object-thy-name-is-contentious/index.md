---
draft: false
title: Network Object, Thy Name is Contentious
description: The world of Information Technology is not spared from the agony of the naming process.
  Discussions involving naming and numbering conventions can turn into...
summary: Go Ahead, create a naming convention. I dare you.
# summary:  The world of Information Technology is not spared from the agony of the naming process.
#   Discussions involving naming and numbering conventions can turn into...
date: 2023-06-18T21:12:00-06:00
categories:
  - Opinion
tags:
  - Automation
  - Design
---
---
{{< lead >}}
Go Ahead, create a naming convention. I dare you.
{{< /lead >}}

Have you ever tried to name something - children, pets, a company, a product, etc.? How did it go? What was your process? How long did it take? Naming things can be hard.[^kids] In response to this apparent difficulty, many books have been published to help you name your offspring while countless websites will generate a name for almost anything else.

[^kids]: However, my kids name their stuffies with the greatest of ease.

The world of Information Technology is not spared from the [agony of the naming process](https://www.martinfowler.com/bliki/TwoHardThings.html). Discussions involving naming and numbering conventions can turn into heated debates where it can often feel safer to talk about religion or politics instead. Opportunities abound for naming items in network configuration. Where do you start?

## With RFCs, Of Course

Standards for hostnames have been set for a long time in RFCs [608](https://www.rfc-editor.org/rfc/rfc608.html), [921](https://www.rfc-editor.org/rfc/rfc921), [952](https://www.rfc-editor.org/rfc/rfc952.html), [1123](https://www.rfc-editor.org/rfc/rfc1123.html), and [2182](https://www.rfc-editor.org/rfc/rfc2181.html). By combining different items from these RFCs, I use the following naming convention for hostnames:

- Maximum of 63 characters
- Characters drawn from the alphabet (a-z), digits (0-9), and the minus sign (-)
  - No blank or space characters
- Configure in lowercase
- MUST start with a letter
- MUST NOT end with a minus sign
- Made up of sections delimited by the minus sign
  - Minus sign used exclusively as a delimiter

### Not Just Hostnames

The need for names in networking does not end with hostnames. Objects such as ACLs, VRFs, VLANs, route maps, prefix lists, and class maps all require a name. The convention I use for these is only slightly different than that of hostnames:

- Characters drawn from the alphabet (A-Z), digits (0-9), and the underscore (_)
  - No blank or space characters
- Configure in UPPERCASE
- MUST start with a letter
- MUST NOT end with an underscore
- Made up of sections delimited by the underscore
  - Underscore used exclusively as a delimiter

I was shooting for simplicity[^lazy] with the naming convention for objects. My logic is as follows:

[^lazy]: Or maybe I was being lazy.

- Do not deviate too much from the hostname standard.
- Underscores (_) are used as delimiters in object names to avoid confusion with commands.
  - There are no commands that use underscores but there are commands that use the minus sign (-).[^cisco]
  - Examples of commands with a minus sign are access-lst, class-map, prefix-list, and route-map.
- Most objects are case-sensitive so UPPERCASE is used exclusively to avoid ambiguity and for config readability.
  - UPPERCASE stands out against a wall of lowercase text.
  - The underscore fits nicely into UPPERCASE as it is also accessed using the **shift** key.

[^cisco]: At least in Cisco's world.

## What's In A Name?

Designing the syntax for a naming standard is not too difficult, especially if you are willing to mostly adopt existing standards. The next step is deciding how to construct a name based on that standard and what information should be conveyed in a name. Unless the name is meant to obfuscate everything about the device, some combination of location and function are common inputs for the hostname. Location information is often not useful for network objects, but this is a topic we'll revisit later in this post.

### Location, Location, Location

Including location information in the name serves a couple of purposes. One purpose is to be able to quickly determine which equipment to check while troubleshooting a problem for a customer at a particular site. Another reason is when a technician needs to physically visit network gear. Everyone can be more confident that the boots on the ground are in the right location when the hostname and physical location align.

Unless you're dealing strictly with the [geographic coordinate system](https://en.wikipedia.org/wiki/Geographic_coordinate_system), location information is usually hierarchical. Multinational organizations with thousands of sites may need to include country, province/state/region, city, building, and room number information in the naming convention. Organizations located in a single city or consisting of a single campus only need to include building and room number information. Not wanting to reinvent the wheel, standards such as the [IATA airport code](https://en.wikipedia.org/wiki/IATA_airport_code), the [CLLI code](https://en.wikipedia.org/wiki/CLLI_code), or the [ISO 3166-2 standard](https://en.wikipedia.org/wiki/ISO_3166-2) could be adapted to suit almost any need.

If some of your network gear lives in the middle of nowhere, which is common for utility, mining, oil and gas, and communications industries, the above standards may not apply or may need some extra massaging to be useful. In these cases, the business may have already assigned some moniker or code to the location which can be incorporated into the naming convention.

Network equipment that moves about the planet on planes, trains, automobiles, ships, or spacecraft, has a different challenge. Perhaps incorporating the name of the vessel into its name is the best approach.

### Function, Function, Function

As evidenced by this statement in RFC952, `"A host which serves as a GATEWAY should have "-GATEWAY" or "-GW" as part of its name."`, there was recognition that a device's function should be reflected in its name. The utility of this standard has increased as the list of functions has grown substantially since the 1985 publication date. The following table contains a non-exhaustive list of device functions and associated abbreviations that could be used for naming.

|Function|Abbreviation|
|:----|:----|
|`Access Layer`|`acc`|
|Aggregation Layer|agg|
|Border Router|brdr|
|Core Layer|core|
|Customer Edge|ce|
|Distribution Layer|dist|
|Edge Layer|edge|
|Firewall|fwl|
|Intrusion Prevention System|ips|
|`Leaf Switch`|`lf`|
|Provider Edge|pe|
|Provider Router (MPLS core)|p|
|Spine Switch|spn|
|`Top of Rack Switch`|`tor`|
|Virtual Private Network Concentrator|vpn|
|Wireless Access Point|ap|

Because I treat the access layer as the default function for network gear, I never use the highlighted items from the above table. Instead, a room number in the case of a campus or branch office access switch, or the row and rack number in the case of a Leaf or ToR switch in a DC is the final section in the name. Although wireless access points often function in the access layer, I do use "ap" when naming them.[^logical]

[^logical]: I don't know if Spock would consider this approach to be logical or not.

Redundancy and high availability can also be considered functions. For devices that can work in pairs, such as firewalls, load balancers, and MLAG switches, ending the hostnames with `-1` and `-2` is a common practice. For clustering technologies that support more than two devices, or independent devices that take on more load when other like-systems are down, the numeric suffix on the hostname increases as needed. Clustered firewalls and multiple spine switches in a spine/leaf DC fabric are examples where redundancy can grow beyond two devices. Letters can also be used to designate redundant members of a group, but require more mental math, so I stick with numbers.

#### Object Oriented

Objects are all about functionality and context. VRFs can be allocated for different customers or separate business units of a single organization. VLANs can be instantiated for all different types of traffic. Access lists can be used for filtering traffic at specific interfaces or controlling routing updates. Prefix lists can also be used to control routing information or group network traffic by IP prefixes. Route maps and class maps have different use cases but can reference other objects to define more complex network classification criteria.

Ideally, object names would reflect the specific network function or logic they are trying to accomplish. For instance, VLANs dedicated to production web servers, non-production application servers, or end-user devices should indicate these facts in their respective names.  Standard names for ACLs that restrict SNMP or SSH access to a device should be created. There are too many design-specific examples to cover every possible scenario, but I think you get the idea.

One thing to keep in mind is that an object's name should be specific enough to convey its purpose, but not so specific that minor content changes make the name meaningless or force you to have to recreate it with a new name. This is especially true for route maps, class maps, and policy maps which contain other objects. You'll get more mileage out of a route map used to control routing updates sent to a peer when its name is CONTROL_SUBNETS_TO_PEERX than if its name is PERMIT_STATIC_AND_BGP_BUT_DENY_VPNPREFIXES_AND_GUESTWIRELESS.

My experience with multiple customers has revealed a 50/50 split between organizations that like to indicate the object type in the object's name and those that don't. For example, `_ACL`, `_RMAP`, and `_PREFIX` are suffixes added to access lists, route maps, and prefix lists in some network shops. If you use this convention, know that I'm secretly making fun of you. I don't use this convention because the network configuration already does that for me. Access lists are called with the `access-list` command. Similarly, route maps and class maps are invoked with the `route-map` and `class-map` commands.[^cisco]

## Influenced By Automation

In the glory days of CLI, it was common practice to reuse object names across multiple devices even when those objects held different configurations. Access lists, prefix lists, and route maps that contain locally significant IP information often have the same name across all sites because the function performed by these objects was the same. Centralizing management of these constructs in an automation tool quickly creates an identity crisis. A unique name for unique content is the remedy. For objects that have global, regional, or site significance, one approach is to use applicable location information in the name. For host-specific constructs - those that have the same function on multiple hosts but have different contents - using the hostname in the object's name is one way to provide uniqueness.

Automation also brings the ability to enforce a naming convention through data validation. Names for both hosts and objects should be simple to derive from the naming standard as this simplicity makes automated data validation easier to create. Complexity is a barrier to automation efforts.

## Show Me

To make examples more meaningful, let's create a fictitious organization. Canada consists of [ten provinces and three territories](https://en.wikipedia.org/wiki/ISO_3166-2:CA) with each being responsible for delivering healthcare to their respective populations. We'll pretend that the Canadian federal government has created a new crown corporation to assume control of **all** healthcare facilities in the country. This new organization is headquartered in the TC Douglas building in Regina, SK. Two active/active data centres host most applications and services. Western Canada is serviced mostly by the DC in Calgary, AB while Eastern Canada uses the DC in Montreal, QC. WAN connectivity consists of a mixture of carrier-provisioned MPLS and SD-WAN over the Internet and satellite links.

Hostnames of non-DC network gear will follow the convention of `province/territory-city/town-building-roomnumber` if it operates in the access layer and `province/territory-city/town-building-roomnumber-function` if it doesn't.

Hostnames of DC network gear will follow the convention of `dc-east/west-datahall-rowrack` if it operates in the access layer and `dc-east/west-layer-function` if it doesn't.

|Name|Description|
|:----|:----|
|sk-regn-tcdg-201|Access switch in room 201 of the TC Douglas building in Regina, SK|
|on-tnto-tgh-1834|Access switch in room 1834 of the Toronto General Hospital in Toronto, ON|
|bc-kmlp-chcl-ap|WAP in the Cherry Clinic in Kamloops, BC|
|dc-west-sdwan-2|SD-WAN hub router 2of? in the Western DC|
|dc-east-inet-fwl-1|Internet edge firewall 1of? in the Eastern DC|
|dc-east-int-ips-2|Internal IPS 2of? in the Eastern DC|
|EAST_SNMP_ACCESS|ACL present on all network gear in Eastern Canada to control SNMP access|
|WEST_SNMP_ACCESS|ACL present on all network gear in Western Canada to control SNMP access|
|ON_TNTO_TGH_0110_BRDR_TO_MPLS|Route map on the border routers in the Toronto General Hosptial to control updates to the carrier|
|ON_TNTO_TGH_0110_BRDR_ROUTES|Prefix list on the border routers in the Toronto General Hosptial called by the above route map|

## That Wasn't So Bad

I've been using some form of this naming convention for many years now. Even with that experience under my belt, it was still difficult to create the examples above, and I see good reasons to make little changes here and there. Add a few more people to standards creation, each with their own experience and use cases, and you have a recipe for some long, and sometimes intense, conversations.

Naming isn't the most exciting work, but it is important. A good naming convention should remove bottlenecks by providing autonomy for operators to make naming decisions, and it should help the network be self-documenting.
