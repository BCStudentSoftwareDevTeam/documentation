---
title: Infrastructure
description: Details of our network and servers
published: true
date: 2019-10-17T15:50:54.987Z
tags: 
---

# Physical Servers

## IS&S - VM hypervisor

* Hosts production VMs for most student [applications](/applications)
	* Advancement
	* BCSR
	* CAS
	* Labor Status Forms
	* Chemical Inventory
	* URCPP
* New VMs created by request to IS&S

## CS - production VM hypervisor
* Hostname: fee
* 10.40.16.12
* Hosted in IS&S rack
* Hosts student, class, and faculty VMs
* Hosts a few production application vms  
	* BCAC
	* Ulmann Archives
	* Wiki.js
* Runs DNS server for resolving \*.ssdt.berea.edu *in progress*

## CS - dev VM hypervisor
* Hostname: ada
* 10.40.132.97
* Hosted in ssdt room *temporarily*
* Used for testing upgrades and deployment scripts

## External site - cs.berea.edu
* Hosted by IS&S
* Content controlled by CS


# Virtual Machines

## Ansible

Our physical and virtual servers are provisioned with Ansible. [View Ansible repository](https://bitbucket.org/laborstudents/ansible_proj/src/master/). 

Instructions for use can be found in the [README](https://bitbucket.org/laborstudents/ansible_proj/src/master/README.md).

## libvirt
