---
title: Cipollino, an AS-aware Tor client
image: /img/cipo.png
description: Designing an AS aware client immune to active and passive attacks from network-level adversaries.
people:
  - rishab
  - rachee
  - shinyoung
  - phillipa

layout: project
status: inactive
---

Traffic correlation attacks to de-anonymize Tor users are possible when an adversary is in a position to observe traffic entering and exiting the Tor network. We focus on addressing the problem of traffic correlation attacks by network-level adversaries (Autonomous Systems (ASes)). Cipollino leverages public sources of empirical routing data and the latest developments in network-measurement research to defend against currently known types of network-level traffic correlation attacks, including attacks by active adversaries that may exploit BGP insecurities to de-anonymize Tor clients. Cipollino is able to reduce the number of vulnerable webpage loads to just 1.3% from vanilla Tor's 57%. In terms of performance, under aggressive configurations, the Cipollino client is able to match the page-load times of the vanilla Tor client and significantly improve on previous AS-aware Tor clients, even in its most conservative configuration. Additionally, Cipollino retains security against relay-level adversaries. Finally, like previous AS-aware Tor clients, Cipollino is able to perform load-balancing to avoid overloading relays. 
