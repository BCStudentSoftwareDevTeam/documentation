---
title: Production Servers
description: How to set up production servers
published: true
date: 2020-05-01T11:05:18.579Z
tags: infra
---

# Setting Up Production Servers
A guide to setting up production servers, for security and repeatibility. We really should get to the point where all of this is automatically done by Ansible.



## Security
Only necessary packages should be installed and only necessary services should be running. Run `nmap URL` to check and see what ports are open on your server.

### Unattended Upgrades
Security updates should be installed automatically. For our older servers using Ubuntu 16.04, this document outlines the steps: https://linoxide.com/ubuntu-how-to/enable-disable-unattended-upgrades-ubuntu-16-04/.

### SSL
Production webservers should use SSL only. An example Apache configuration to disable http access is here:

    <VirtualHost *:80>
            ServerAdmin ramsayb2@berea.edu
            ServerName cas.berea.edu
            Redirect permanent / https://cas.berea.edu/
    </VirtualHost>



If the server is accessible off campus we can use [Lets Encrypt](https://letsencrypt.org/). If not, we will need to get a certificate and set it up manually.

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

To automatically add SSL or switch to Let's Encrypt as the certificate issuer, run certbot and follow the prompts:

    sudo certbot --apache
    
Test that renewal will work: `sudo certbot renew --dry-run`.
Verify that the renewal is scheduled with systemd: `systemctl list-timers`.

#### Manual
<Coming Soon\>


## Authentication

### SSH

### Shibboleth

## Backups

