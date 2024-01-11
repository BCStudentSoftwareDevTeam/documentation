---
title: LSF User Management
description: 
published: true
date: 2024-01-11T18:47:47.257Z
tags: 
editor: markdown
dateCreated: 2024-01-11T18:47:47.257Z
---

# LSF Users
LSF users can be supervisors (faculty and staff), or students. Administrator permissions are set in the application. LSF uses both preferred name and legal name in different places. 

Automatic syncing daily via cron. Log in `/home/lsf/cron.log`.

## Importing Users

This application uses data from both UltraTime and LDAP. 

The script [`scripts/updateDBRecords.py`](https://github.com/BCStudentSoftwareDevTeam/lsf/blob/development/scripts/updateDBRecords.py) will sync students and supervisors from UltraTime, retrieving all records found in UltraTime and updating the corresponding records in the `Student` and `Supervisor` tables, adding if necessary.

The script [`scripts/sync_preferred_name.py`](https://github.com/BCStudentSoftwareDevTeam/lsf/blob/development/scripts/sync_preferred_name.py) will retrieve names from LDAP for students and faculty or staff, and update `preferred_name` in the relevant lsf table (`Student` or `Supervisor`).

The scripts must be run in tandem, and in this order, in order for preferred name preferences to be preserved.
 
 ## User Permissions
 
There are 5 types of permissions, Administrators (Labor, SAAS, or Financial Aid), Supervisors, and Students. Administrator permissions can be updated in the application admin page: https://lsf.berea.edu/admin/adminManagement. Supervisor and Student permissions are not alterable.