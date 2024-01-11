---
title: CAS User Management
description: 
published: true
date: 2024-01-11T19:41:35.941Z
tags: 
editor: markdown
dateCreated: 2024-01-11T19:41:35.941Z
---

# CAS Users
CAS users can be faculty or staff. Permissions are set in the application.

Automatic syncing daily via cron.

## Importing Users

The script [`sync_faculty.py`](https://github.com/BCStudentSoftwareDevTeam/cas/blob/development/sync_faculty.py) will sync both faculty and staff from LDAP to the URCPP database. It first loads a temporary SQLite table with data from LDAP, and then updates users' bnumbers (but not names!?) or adds user records as needed in the application database.

>Does not update a user's name after reading from LDAP if the user already exists, so no preferred name updates will happen.
{.is-danger}

>LDAP query doesn't handle descriptions beyond 'Faculty', 'Staff', and 'Staff|Faculty'.
{.is-danger}

 ## User Permissions
 
 Users can be Program Chair, Division Chair, Building Manager, or Administrator. These permissions can be adjusted on the User Management page: https://cas.berea.edu/admin/userManagement.
 