---
title: Future Planning
description: Upcoming SSDT projects, upgrades, improvements, and wishlists.
published: true
date: 2019-10-15T20:03:09.695Z
tags: 
---

# Infrastructure
New servers, new networking, new authentication, new support scripts

## Create new base VM
* Ubuntu 18.04 LTS
* Layer requirements (base, application, dev)
* Easy tools to create new and clone from

## Upgrade fee
* Ubuntu 18.4 LTS and latest libvirt
    * Add domain lookup to hosts https://libvirt.org/nss.html
    * Add DNS server https://liquidat.wordpress.com/2017/03/03/howto-automated-dns-resolution-for-kvmlibvirt-guests-with-a-local-domain/
    * virsh and libvirt shouldn't need sudo
* Add a development and staging machine to test upgrades (currently ada: 10.40.132.97)

# Application Development
Changes to improve the quality of or add new features to our applications.

## Fast Dev Deployments
* Base VM with appropriate configuration
    * docker.io, docker-compose, mysql, sudo access, ssh set up, user in docker group
* config in git repo and setup.sh should create sensible dev defaults
* database should be set up easily and as automatically as possible
    * import existing prod database
* Provide Docker container for fast startup
* Applications should be consistently configured where possible
* Proper Documentation present in README
* Easy to run test builds
* No extraneous or outdated files in repo root

# Wishlist
We need to do these things eventually, either for our applications' sake or our own sanity.

## Tests!
* We need a test framework and an easy entry point to write new tests for features

## Continuous Integration
* Build Server
* Acceptance Testing Framework
* Smoke tests for each application
* Physical indicators of build health

## Continuous Delivery
* Staging Environment for each application
* Reliable deployment process for each application
* Pipeline

## Repo Cleanup
* No outdated files (scripts, cleanup, db management)
* Up-to-date documentation

## Log Management
* Centralized log viewer
* Alerts based on log events

## SSH Key Management
   * Investigation
	* https://www.bastillion.io/docs/using/whitepaper/
	* authpush

## Ansible Best Practices
* re-organize ansible repository
* playbooks shouldn't need sudo

## Migrate applications from IS&S hypervisor to fee
* We should control production applications

## Standardize application configuration and deployment
* Flexible configuration
	* Sensible defaults
	* Environment switching
	* Local overrides
* wsgi_express with docker?

# Completed
For posterity. See how far we have come.

## New Documentation Platform
* Wiki.js server
    * Ansible start script
    * Docker-based
    * Persistent volumes
    * URL, not IP
* Backed by git repo in ssdt bitbucket
* New Developer Orientation documentation
* High level application details

