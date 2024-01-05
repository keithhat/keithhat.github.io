---
layout: post
title:  "Devices"
#date:   2024-01-03 20:00:34 +1100
#categories: [home, devices]
#layout: page
permalink: /devices/
---

# Background

This page is to track my network topology and major devices.

My home has the following complications that impacted the topology:
- The study does NOT allow wifi to penetrate due to double brick walls.
- The FTTB supplier really needs a specific modem/router which didn't have features I wanted in my main router.


# Topology

```
Modem (Router Disabled)
    +-- Ethernet
        +-> Router (Living Room)
            +-- WiFi (2.4 / 5)
            +-- Ethernet
                +-> RPI
                +-> PoE Adaptor (Living Room)
                    ...
                    PoE Adaptor (Study)
                        +-- Ethernet
                            +-> Router (Study)
```


# Main Devices 

| Name | Details | IP | Notes |
| --- | --- | --- | --- |
| Modem | TP-Link Archer VR1600v | 192.168.1.1 | ISP Supplied |
| Router (Living Room) | TP-Link AX1800 | 192.168.7.6 | SSIDs: {::nomarkdown}<ul><li>'Keithy' 5GHz</li><li>'Keithino' - 2.4GHz</li></ul>{:/} |
| RPI Server | RPI 4B | 192.168.7.123 |Running: {::nomarkdown}<ul><li>Pi-Hole</li></ul>{:/}
| Router (Study) | TODO | TODO | SSIDs: {::nomarkdown}<ul><li>'Keithy' 5GHz</li><ul>{:/} |
| PoE | TODO | N/A |  |



