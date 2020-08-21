---
title: Future Planning
description: Upcoming SSDT projects, upgrades, improvements, and wishlists.
published: true
date: 2020-08-21T18:10:31.650Z
tags: 
---

# Infrastructure In Progress
New servers, new networking, new authentication, new support scripts.

## Create new base VMs
* Ubuntu 18.04 LTS
* Layer requirements (base, application, dev)
	* Base should be minimal
  * Application bases should have the necessary packages and configuration for particular types of applications (e.g., flask, docker)
  * Dev base should have the tools to support a wider variety of development. Multiple shells, editors, different web serving methods
* Easy tools to create new and clone from bases
* Existing student and system creation tools should still work

## Upgrade fee
* Ubuntu 18.4 LTS and latest libvirt
  * Add domain lookup to hosts https://libvirt.org/nss.html
  * Add DNS server https://liquidat.wordpress.com/2017/03/03/howto-automated-dns-resolution-for-kvmlibvirt-guests-with-a-local-domain/
  * virsh and libvirt shouldn't need sudo
  * accounts for admins
* Add a development and staging machine to test upgrades (currently ada: 10.40.132.97)
	* Create ansible playbook to provision server from scratch (and maintain it)
  * Migration Plan

## Log Management
* Centralized log viewer
* Alerts based on log events
  * Nagios - https://www.nagios.org/
  * Sensu - https://sensu.io/
  * ELK Stack - https://www.elastic.co/products/
  * Graylog - https://www.graylog.org/products/open-source

## Continuous Integration
* Build Server
* Acceptance Testing Framework
* Smoke tests for each application
* Physical indicators of build health
* Accessible Dashboard
* Investigation
	* https://travis-ci.com/
  * https://education.travis-ci.com/
  * https://jenkins.io/

# Application Development in Progress
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

## Continuous Delivery
* Staging Environment for each application
* Reliable deployment process for each application
* Pipeline
	* https://jenkins.io/solutions/pipeline/
  * https://plugins.jenkins.io/pipeline-utility-steps
  * https://plugins.jenkins.io/job-dsl
  * https://stackify.com/continuous-delivery-git-jenkins/
  * https://docs.travis-ci.com/user/build-stages/

## Repo Cleanup
* No outdated files (scripts, cleanup, db management)
* Up-to-date documentation

## SSH Key Management
* Ability to add and revoke permissions to servers
* Avoid having to email private keys
* Use existing user keys
* Investigation
	* https://www.bastillion.io/docs/using/whitepaper/
	* authpush

## Ansible Best Practices
* re-organize ansible repository
* playbooks shouldn't need sudo


## Standardize application configuration and deployment
* Flexible configuration
	* Sensible defaults
	* Environment switching
	* Local overrides
* wsgi_express with docker?

## Training
* Documentation for common software development knowledge
  * git, linux CLI, ssh, docker
  * code reviews, testing, CI
* Training path that includes problems to solve

## Web-based VM Management
* View status of VMs
* Create single or multiple VMs at once
  * Limit base VM options for security
* Associate VMs & images with creators and users
* View VM detail
  * Guest OS Info
  * Users
  * VM Info
  * Resource Utilization
* View host status
  * CPU, memory, storage
* Clean up unused VMs
* https://github.com/kimchi-project/kimchi?

## Application Accessibility
* Analyze application for accessibility issues
* Find resources for fixing problems
* Conferences?
  * https://accessinghigherground.org/
  * https://www.csun.edu/cod/conference

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

## Labor Status Forms Rewrite
* Get LSF rewritten as a Flask application
* All hands on deck

