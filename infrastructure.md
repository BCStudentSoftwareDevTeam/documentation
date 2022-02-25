---
title: Infrastructure
description: Details of our network and servers
published: true
date: 2022-02-25T15:25:51.134Z
tags: 
editor: markdown
dateCreated: 2019-10-15T16:42:57.959Z
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
* Runs DNS server for resolving \*.ssdt.berea.edu *(in progress)*

## CS - dev VM hypervisor
* Hostname: ada
* 10.40.132.97
* Hosted in ssdt room *(temporarily)*
* Used for testing upgrades and deployment scripts

## External site - cs.berea.edu
* Hosted by IS&S
* Content controlled by CS


# Virtual Machines

## Ansible

Our physical and virtual servers are provisioned with Ansible. [View Ansible repository](https://bitbucket.org/laborstudents/ansible_proj/src/master/). 

Instructions for use can be found in the [README](https://bitbucket.org/laborstudents/ansible_proj/src/master/README.md).

## libvirt

We use `virt-builder`, `virt-install`, and `virt-customize` to modify virtual machine images in place.

There is currently a problem with these `libguestfs` tools, where they can't resize logical partitions. This means we have to manually resize our base image after creation, rather than being able to have it happen automatically in a script. Here are the steps to resize the disk:

* Resize the disk (located in `/var/lib/libvirt/images/`): `qemu-img resize base.img 32G`
* Start the VM and log in
* Expand the partitions: https://unix.stackexchange.com/a/320454
* Resize the filesystem: `resize2fs /dev/vda5`