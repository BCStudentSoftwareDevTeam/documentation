---
title: New BCSR user
description: 
published: true
date: 2023-05-10T19:41:49.946Z
tags: 
editor: markdown
dateCreated: 2023-05-10T19:41:49.946Z
---

1. SSH into bcsr.berea.edu
1. Switch to root with `sudo su`
1. `cd` to application directory (currently `/var/www/html/bcsr-flask/`
1. Edit `add_user.py` with the new user information
1. Run `source setup.sh` to set up your virtual environment
1. Run `python add_user.py`