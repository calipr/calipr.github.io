---
title: PathCache
image: /img/pathcache.png
description: PathCache bootstraps from publicly available measurement data to predict paths between arbitrary source and destination Autonomous Systems on the Internet.
people:
  - rachee
  - phillipa

layout: project

---
PathCache is a system that provides path prediction as a service. PathCache bootstraps off of multiple empirical data sets, combining them to pre- dict paths that have not been directly measured. PathCache provides higher accuracy path prediction than algorithmic simulations (BGPSim) that have been used in the past. We recently built a prototype for PathCache and based on our evaluation of the system on high traffic (eyeballs to content) paths, PathCache is able to accurately predict Autonomous System (AS)-level paths (over 80% exact matches). PathCache achieves this without running measurements of its own and relies only on publicly available traceroute data from measurement platforms like RIPE Atlas, CAIDA Ark, PlanetLab etc. In addition to data plane measurements, we supplement our knowledge of paths with BGP updates and RIB dumps from different route collectors on the Internet. This ensemble of datasets gives us high coverage in terms of the number of high traffic paths that we can predict. We plan to integrate BGP looking glass servers (spread across nearly 1000 ASes) into PathCache to increase our coverage further. This prototype is ready for use and we intend to release the code and the deployed service to the community shortly.
<img src="{{site.base}}/img/pathcache.png" class="pull-right" style="width:150px;margin:15px"/>
