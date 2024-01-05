---
layout: post
title: "PI Server"
date:   2024-01-03 21:00:34 +1100
categories: [rpi, pi-hole]
#layout: page
permalink: /rpi/
---

# Goals
I had an existing RPI4B on my network which I've forgotten what is running on it (and likely several years since the last update)
I don't have a good inventory of what was setup on it, so my plan is to deprecated it and track what is running on it. I expect to have the following:
- PiHole
- Apache WebServer for misc future projects
- Externally accessible - router should register the dynamic IP with a service
- Potentially: VPN for rest of the network


# Basic Info 

This is running on a RPI 4B
- RAM: 4GB
    - This can be checked by running:
    ```
    free --mega
    ```
- SD-Card Size: 64GB
- Operating System: Raspbian 64-bit <https://www.raspberrypi.com/software/>
- IP: 192.168.7.123

# PiHole

### Summary

Pihole blocks adds and trackers for any devices on the network. It does need to be setup to serve the new DNS server though.

- [Management Web Console](http://192.168.7.123/admin/)
- [Disable for 5min](http://192.168.7.123/admin/api.php?disable=300&auth=5903077296833e5698359f480566ec3a65e9b4122745376c256343275afe9a40
Project)
- [Pi-Hole Project Homepage](https://pi-hole.net/
Config)

### Setup
I largely followed the tutorial on: <https://www.crosstalksolutions.com/the-worlds-greatest-pi-hole-and-unbound-tutorial-2023> with the following modifications:

- I kept the DHCP on the server rather than static as in the tutorial
- The installer added lighttpd as a webserver.
- There is NO alternative DNS Server - the tutorial setup .52 - I expect .50 was an existing PiHole they had.
- Ensure you setup the PiHole on the DHCP Server DNS details, NOT the WLAN: <https://www.reddit.com/r/pihole/comments/oolfv1/tplink_ax1800_router_automatically_changes_its/>
- I did NOT setup unbound

### Maintenance

- To confirm everything is working <https://d3ward.github.io/toolz/adblock.html>
  To Update:
  ```
  sudo pihole -up
  ```