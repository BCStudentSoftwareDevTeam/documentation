---
title: New BCSR user
description: 
published: true
date: 2024-01-11T19:55:25.048Z
tags: 
editor: markdown
dateCreated: 2023-05-10T19:41:49.946Z
---

# BCSR Users
BCSR users can be faculty or staff (but are usually faculty). Permissions are set in the application.

## Importing Users

Most users are instructors who are imported when adding courses for a new term (see: [Add courses for upcoming term](/runbook/add-term)). Sometimes instructors must be added manually.

1. SSH into bcsr.berea.edu
1. Switch to root with `sudo su`
1. `cd` to application directory (currently `/var/www/html/bcsr-flask/`
1. Edit `add_user.py` with the new user information
1. Run `source setup.sh` to set up your virtual environment
1. Run `python add_user.py`

>No capability for updating names unless the username has also changed AND the user is an instructor on an upcoming course (then a new record will be created).
{.is-danger}

 ## User Permissions
 
Administrators can add and remove administrators on the System Management page: https://bcsr.berea.edu/admin/systemManagement
