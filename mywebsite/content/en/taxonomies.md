---
title: "Taxonomy and Tagging Guide"
description: "Usage guidelines to maintain a consistent classification of the lab content."
---

This page defines how the project's tags should be used in order to keep navigation clear, consistent, and scalable.

The goal is not to add tags for the sake of it, but to create a structure that makes it possible to:

- find content quickly
- avoid duplicates and unnecessary synonyms
- clearly distinguish between tools, functions, and context
- maintain stable naming as the lab grows

---

## General principles

### 1. Tags should not be improvised

Before creating a new tag, it is worth checking whether an equivalent one already exists, or at least one that is close enough.

Example:

- Use `reverse-proxy`
- Do not mix `reverse proxy`, `rev-proxy`, `reverse-proxy-service`

### 2. Tags should follow a common pattern

It is recommended to always use:

- lowercase
- words separated by hyphens
- specific, technical terms

Correct examples:

- `vmware-workstation`
- `ubuntu-server`
- `reverse-proxy`
- `load-balancing`

Examples to avoid:

- `VMware`
- `Ubuntu Server`
- `ReverseProxy`
- `networkstuff`

### 3. Tags must clearly distinguish between tool and function

This is the most important rule.

- **software** = a specific product, system, tool, or platform
- **services** = a technical function or capability provided by something

Examples:

- `opnsense` → software
- `routing` → service
- `firewall` → service

- `unbound` → software
- `dns` → service

- `haproxy` → software
- `reverse-proxy` → service
- `load-balancing` → service

### 4. Fewer tags is better

It is preferable to use a small number of well-maintained tags rather than many ambiguous or overlapping ones.

---

## Taxonomies used

## 1. `software`

### What it represents

Tools, operating systems, products, or specific platforms.

### Why it exists

It makes it possible to group all content related to a specific technology, regardless of the phase or the type of document.

It helps answer questions such as:

- Which project content uses OPNsense?
- Which procedures are related to Ubuntu?
- Which incidents have appeared with VMware?

### What should go here

- operating systems
- hypervisors
- firewalls
- proxies
- observability tools
- cloud platforms
- automation software

---

## 2. `services`

### What it represents

Technical functions or capabilities provided by part of the lab.

### Why it exists

It makes it possible to search content by the function being implemented or troubleshot, regardless of which specific tool is used for it.

It helps answer questions such as:

- Which content is about DNS?
- Which incidents affected the firewall?
- Which procedures exist for proxy or load balancing?

### What should go here

- networking functions
- security functions
- service publishing functions
- observability functions
- continuity and remote access functions

---

## 3. `kind`

### What it represents

The type of content.

### Why it exists

It makes it possible to separate the nature of the document, not its technical content.

This helps answer questions such as:

- Is this a phase, an incident, or a procedure?
- Do I want to see only technical decisions?
- Am I reading a repeatable guide or a project reflection?

### Example values

- `overview`
- `phase`
- `procedure`
- `incident`
- `decision`
- `note`
- `roadmap`

> Recommendation:
>\
> Use this taxonomy with strong discipline and only a few values.
>\
> It is not a good idea to invent new types if a sufficiently clear one already exists.

---

## 4. `phase`

### What it represents

The project stage in which that content appears or makes sense.

### Why it exists

It makes it possible to connect procedures, incidents, and decisions with the moment in the lab when they appeared.

It helps answer questions such as:

- Which content belongs to phase 2?
- Which incidents appeared in phase 3?
- Which procedures were created during phase 4?

### Recommended format

Use a consistent format, for example: `phase-xx`

---

## 5. `network_areas`

### What it represents

The network zone or segment affected by the content.

### Why it exists

It makes it possible to classify content according to the part of the lab it affects, regardless of the software or service involved.

It helps answer questions such as:

- Which configuration affects the client network?
- Which incidents occurred in the DMZ?
- Which procedures affect the backup segment?

> Recommendation:
>\
> Use this taxonomy when the content clearly affects one or more network zones.
>\
> There is no need to force it if the content is completely general.

---

## About separating taxonomies by content type

To prevent procedures and incidents from sharing taxonomy pages and becoming mixed together, the project uses internally separated taxonomies depending on the content type.

For example:

### Procedures

- `p_software`
- `p_services`
- `p_phases`

### Incidents

- `i_software`
- `i_services`
- `i_phases`
- `i_issue_types`

This allows a tag such as `dns` to continue existing in both contexts without mixing together in navigation:

- procedures about DNS
- incidents about DNS

The idea is to keep the **terms** the same, while separating the **context**.

This is done without the user ever being aware that this separation exists, which allows smoother and more organised navigation and content discovery.

---

## Short list of recommended tags

This list is not intended to be exhaustive.  
Its goal is to serve as a quick reference so that new tags do not have to be invented unnecessarily.

## Software

- `vmware-workstation`
- `opnsense`
- `ubuntu`
- `ubuntu-server`
- `unbound`
- `dnsmasq`
- `squid`
- `haproxy`
- `nginx`
- `docker`
- `kubernetes`
- `grafana`
- `prometheus`
- `github-pages`
- `hugo`

## Services

- `routing`
- `dhcp`
- `dns`
- `firewall`
- `nat`
- `internet-access`
- `network-segmentation`
- `vlan`
- `web-server`
- `forward-proxy`
- `reverse-proxy`
- `load-balancing`
- `caching`
- `vpn`
- `monitoring`
- `logging`
- `dashboard`
- `backup`
- `restore`
- `load-testing`

## Kind

- `overview`
- `phase`
- `procedure`
- `incident`
- `decision`
- `roadmap`

## Phase

- `phase-xx`

## Network areas

- `management`
- `clients`
- `servers`
- `iot`
- `dmz`
- `backup`
- `offsite`
- `cloud`

---

## Practical examples

## Example 1: procedure

A procedure for configuring Unbound as the primary DNS could use:

- software: `opnsense`, `unbound`
- services: `dns`
- kind: `procedure`
- phase: `phase-2`
- network_areas: `clients`, `management`

## Example 2: incident

An incident related to access to the OPNsense GUI could use:

- software: `opnsense`
- services: `firewall`, `routing`
- kind: `incident`
- phase: `phase-2`
- network_areas: `management`

---

## When to create a new tag

A new tag should only be created if it:

- describes something that is not already well covered
- is going to be reused
- is not just a synonym of an existing one
- clearly fits within a specific taxonomy

Before creating it, it is worth asking:

1. Is this a specific tool or a function?
2. Does an equivalent tag already exist?
3. Am I going to use it again?
4. Does its name follow the project's naming pattern?

---

## Summary

The project's classification relies on five main ideas:

- **software**: which tool is involved
- **services**: which function it serves
- **kind**: what type of document it is
- **phase**: which stage of the project it belongs to
- **network_areas**: which part of the lab it affects

Maintaining this structure from the beginning prevents the documentation from becoming inconsistent, hard to navigate, or impossible to maintain.

The priority is not to have many tags, but to have **few, clear, and well-used** ones.