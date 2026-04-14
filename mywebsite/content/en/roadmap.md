---
title: "Roadmap"
---

Given the current developing state of this project, the next exposed phases are subject to change while progress is made. Specialy the farther away these are from the current state. The current working phase is going to be marked between asteriscs (*).

## Phase 0 - Infrastructure

- Setup the enviroment for using VMware Workstation as virtualization client.
- Creation of virtual networks diferentiated by function. [More info.](../arch/_index.en.md)
- Search of ISO images and resources alocation for the virtual machines.

## \* Phase 1 - Initial Setup \*

- Initial deployment and basic configuration of:
    - 1 Ubuntu Client
    - 1 Ubuntu Server
    - 1 OPNsense router
- Configure OPNsense as principal DHCP server following the planned architecture.
- Basic validation of connectivity accesing a basic web from the ubuntu server.

## Phase 2 - Firewall and DNS

- Configure the firewall to allow only specific traffic.
- Configure OPNsense DNS as primary option.
- Add Internet access and check that firewall rules and DNS resolution works as intended.

## Phase 3 - Local DNS and forward proxy

- Configure local DNS entry for web.lab.local to the local web server.
- Install and configure Squid forward proxy in OPNsense.
- Bind it to the client network.
- Enable cache and verify repeated requests are faster.

## Phase 4 - Reverse proxy and load balancing

- Add a second backend web server.
- Install and configure HAProxy as reverse proxy.
- Create a frontend entry such as app.lab.local.
- Configure backend pool with web01 and web02.
- Enable health checks.
- Stress test the reverse proxy and observe behavior in the HAProxy stats dashboard.
