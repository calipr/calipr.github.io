---
title: Politics of Routing
image: /img/as-topo.png
description: Relating characteristics of Internet topologies of countries with their Internet freedom.
people:
  - rachee
  - phillipa

layout: project

---
As part of this study, we investigate the relationship between national policies around freedom of speech and Internet topology in various countries.
We combine techniques from network measurement and machine learning to identify features of Internet structure at the national level that are the best indicators
of a country’s level of freedom. Some of our findings were published in [The Politics of Routing: Investigating the Relationship Between AS
Connectivity and Internet Freedom] (https://people.cs.umass.edu/~phillipa/papers/foci16-final16.pdf) at USENIX FOXI 2016.

An interesting from the data-plane and control-plane based AS topologies of countries inferred as part of this study is that countries where one (or few) AS is *central*
to providing international connectivity, can implement information controls with greater ease. For instance, in Bahrain's Internet topology (blue nodes are international
ASes and red nodes are Bahrain's ASes), one AS provides most of the international connectivity:

<img src="{{site.base}}/img/bh-topo.png" style="justify-content:center;margin:15px;width:70%"/>

Currently, we are performing a logitudinal analysis of changes in the Internet topologies of countries over the last 5-7 years and finding
characteristics of the topologies that can be predictive of changes in Internet Freedom.