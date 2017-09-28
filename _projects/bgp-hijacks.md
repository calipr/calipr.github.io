---
title: Detecting BGP Hijacks and Interceptions
image: /img/bgp-hijack.png
description: Building tools for real-time detection of BGP hijacks and interceptions.
people:
  - shinyoung
  - phillipa

layout: project

---
Devising effective methodologies for the detection and characterization of traffic interception events requires empirical and timely data. Such data must be a combination of passive BGP measurements and active measurements (such as traceroutes), since the mechanism triggering the attack operates on the inter-domain routing control plane, but the actual impact is only verifiable in the data plane. In this project we seek to: (i) investigate, develop, and experimentally evaluate novel methodologies to automatically detect traffic interception events and to characterize their extent, frequency, and impact; (ii) extend our measurement infrastructure to detect in near-realtime and report episodes of traffic interception based on BGP hijacking; (iii) document such events, providing datasets to researchers as well as informing operators, emergency-response teams, law-enforcement agencies, and policy makers. We will quantify increased latency along observed paths, the magnitude of the incident in terms of number of ASes and prefixes intercepted, and the social/political implications of interceptions that take traffic across national borders. To better understand the both technical and political effects of hijacks, we will augment our active measurement framework with algorithmic simulations of BGP routing policies, and qualitative analysis of the organizations involved.
