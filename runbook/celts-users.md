---
title: CELTS User Management
description: 
published: true
date: 2024-01-11T18:34:22.235Z
tags: 
editor: markdown
dateCreated: 2024-01-11T18:34:22.235Z
---

# CELTS Users
CELTS users can be faculty, staff, or students. Permissions are set in the application. CELTS uses preferred name everywhere instead of legal name. 

Automatic syncing daily via cron. Log in `/home/celts/cron.log`.

## Importing Users

This application uses data from both UltraTime and LDAP. First, it retrieves the set of users from UltraTime (with names, majors, and class levels) and updates the User table. It then retrieves the users from LDAP in order to get preferred name, and updates the User table if necessary.

The script [`app/scripts/import_users.py`](https://github.com/BCStudentSoftwareDevTeam/celts/blob/development/app/scripts/import_users.py) will sync users from both LDAP and UltraTime.

 
 ## User Permissions
 
There are three tiers of permissions, CELTS Admin, Student Admin, and Student Staff. User permissions are managed in the application admin pages: https://celts-link.berea.edu/admin. Students can also be listed as Program Managers, which will give them access to admin functionality for specific CELTS programs.