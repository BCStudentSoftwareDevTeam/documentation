---
title: Production Servers
description: How to set up production servers
published: true
date: 2020-05-01T01:38:29.125Z
tags: infra
---

# Setting Up Production Servers
A guide to setting up production servers, for security and repeatibility.



## Security

### SSL
Production webservers should always use SSL. If the server is accessible off campus we can use [Lets Encrypt](https://letsencrypt.org/). If not, we will need to get a certificate and set it up manually.

#### Lets Encrypt
Check up to date instructions from letsencrypt: https://certbot.eff.org/instructions. The gist is as follows.

Add the CertBot PPA

    sudo apt-get update
    sudo apt-get install software-properties-common
    sudo add-apt-repository universe
    sudo add-apt-repository ppa:certbot/certbot
    sudo apt-get update
    
Install CertBot
	
    sudo apt-get install certbot python3-certbot-apache


#### Manual

### Unattended Upgrades

## Authentication

### SSH

### Shibboleth

## Backups

