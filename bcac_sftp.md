---
title: BCAC SFTP Setup
description: 
published: true
date: 2021-04-22T20:18:02.057Z
tags: 
---

# BCAC SFTP

There is an SFTP user on bcac.berea.edu that can edit pawtucket files, and only pawtucket files. `sftp sftp@bcac.berea.edu`. The art department, Brian Ramsay, and Scott Heggen have the password.

## Details
The `sftp` user cannot log in via SSH, only sftp. Their home directory is `/home/sftp`. The pawtucket directory is mounted inside. It's possible the mount will need to be recreated after restart - not sure about this.

## Creation

- Create an SFTP user: 

<code>
$ groupadd sftp_users
$ useradd -g sftp_users -G www-data -d -m -s /sbin/nologin sftp
$ passwd sftp
</code>

- Create a pawtucket directory they can edit: `mount --bind /var/www/html/art-archives-1.7.8/pawtucket pawtucket`
- Add to `/etc/ssh/sshd_config`:

<code>
Match Group sftp_users
    ChrootDirectory /home/sftp/
    ForceCommand internal-sftp
    AllowTcpForwarding no
    X11Forwarding no
</code>