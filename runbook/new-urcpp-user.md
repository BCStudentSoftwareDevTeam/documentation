---
title: URCPP Users
description: 
published: true
date: 2024-01-11T14:45:32.164Z
tags: 
editor: markdown
dateCreated: 2024-01-10T21:22:05.116Z
---

# URCPP Users
URCPP users can be faculty or staff. There are unused tables for students in the database. Permissions are set in the application.

Automatic syncing daily via cron.

## Importing Users

The script [`sync_faculty.py`](https://github.com/BCStudentSoftwareDevTeam/urcpp/blob/development/sync_faculty.py) will sync both faculty and staff from LDAP to the URCPP database.

FAILS: 
 - Fails trying to enter duplicates instead of handling name or bnumber changes
 - LDAP query doesn't handle descriptions beyond 'Faculty' or 'Staff'
 
 ## User Permissions
 
 TBD
 