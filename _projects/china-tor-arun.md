---
people:
  - adunna
  - phillipa
layout: project
title:  "Analyzing China's Blocking of Unpublished Tor Bridges"
description: "We determine the extent to which both published and unpublished relays, specifically bridges, are blocked by the GFW."
---

## Abstract

At the end of 2011, China's Great Firewall (GFW) began to block unpublished Tor bridges. Past studies of this blocking have found that the firewall implements both deep packet inspection (DPI) and active probing in order to identify and block usage of the Tor protocol. We build upon the information from previous studies conducted in 2012 and 2015, using a vantage point in China, and bridge relays that we deploy in the US, Canada, and the UK. We determine the extent to which both published and unpublished relays, specifically bridges, are currently blocked by the GFW. We also analyze the active scanners employed by the GFW, and determine the viability of various deployed circumvention methods. We specifically observe that a simple technique to identify and not respond to the GFW's scanners is effective in keeping a bridge relay from being blocked. We conclude by discussing the current circumvention methods, and how best to implement these circumvention methods to improve the accessibility of the Tor based on our measurements.

----

Note that our packet captures are not included for privacy reasons. However, direct exports of filters applied to these captures are supplied in CSVs.

The complete list of files is contained in [this directory](https://adunna.me/projects/dist/foci-2018-tor/), or available in a [compressed ZIP file.](https://adunna.me/projects/dist/foci-2018-tor/files.zip)

We include descriptions of each file:

----

`files.zip` Contains all included directories and files, compressed for download.

## Code

`Code/ping.py` This code creates processes to ping each IP found in the CSV containing public relay IPs. It prints each result. You can export this to a file through a pipe.

`Code/plots.r` Plotting code used to create all [plots](https://adunna.me/projects/dist/foci-2018-tor/Plots/) shown in our paper, as well as some unused ones.

## Data

`Data/analysis-only-SYN.csv` Formatted export of packet capture. It contains TCP packets, filtered to remove packets sent from our Chinese client to the relay. It also removes noise, or any other packets not sent from China to the US. So, it only contains SYN packets sent from Chinese scanners.

`Data/analysis-with-streams.csv` Similar to the previous one, except that packets are not limited to those with the SYN flag, and the TCP stream index is included in the data for each packet.

`Data/userstats-bridge-combined-cn-2012-01-01-2018-05-28.csv` Contains the number of Chinese Tor bridge users per protocol (default, meek, and obfs4) for each day from 01/01/2012 to 05/28/2018.

`Data/userstats-relay-country-2011-01-01-cn-2018-05-29-off.csv` Contains the total number of Chinese Tor relay users per day from 01/01/2011 to 05/29/2018.

`Data/PingResults.txt` Contains results from `Code/ping.py`, showing whether each pinged relay IP was up or down.

## Plots

All plots are generated using the exported capture results. You can therefore assume "packets" to mean packets contained in those results.

`Plots/cdf_ttl.pdf` CDF of TTLs for packets.

`Plots/china_tor_users.pdf` Double line plot showing the number of Tor users over time per meek and obfs4, through daily peaks.

`Plots/ipid_ttl_time.pdf` A scatter plot with two axes for showing each packet's IPID and TTL. This was to determine any IPID patterns.

`Plots/probe_map.pdf` A map of China using *rworldmap*, meant to display the wide variety in geo-locations of scanner IPs.

`Plots/scans_per_ip.pdf` Bar plot using *geom_histogram* with the stream-limited dataset described in `Code/plots.r`, to show the number of scans from each IP.

`Plots/syn_count_dist.pdf` Density plot for the number of SYN packets seen from each IP.

`Plots/syn_times.pdf` An experimental plot for showing which times SYN packets were received / not received. Each vertical blue line represents a received packet.

`Plots/syn_times_2.pdf` A more readable version of the previous plot for showing times that SYN packets were received. This shows the number of packets received each hour through a line plot.

`Plots/ttl_by_mss.pdf` TTLs for packets, categorized by MSS value in a bar plot.

## Resources

`Resources/GeoLite2-City.mmdb` MaxMind GeoLite2 City database for geolocation.

`Resources/PUBLIC_RELAYS_STRIPPED-04-23-2018.csv` A list of all Tor relay IPs on 04/23/2018, obtained through scraping the public Tor consensus.

`Resources/tcis_run` A compiled binary of [tcis](https://github.com/NullHypothesis/tcis).
