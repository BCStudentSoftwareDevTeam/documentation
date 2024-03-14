---
title: Scheduled Jobs
description: 
published: true
date: 2024-03-14T19:05:05.490Z
tags: 
editor: markdown
dateCreated: 2024-03-14T18:51:17.153Z
---

# Scheduled Jobs

## Production Notification

Schedule: **Every 5 minutes**
Location: **root@fee**
Method: **cron**

Messages the #bosschannel in the Student Programmers slack if any of our production systems are down. Runs https://github.com/BCStudentSoftwareDevTeam/infra/blob/main/monitoring/getSiteActivityScript.sh.

## LSF - Update Student Records
Schedule: **4am every day**
Location: **lsf@lsf**
Method: **cron**

Updates preferred name from LDAP. Runs https://github.com/BCStudentSoftwareDevTeam/lsf/blob/production/scripts/sync_preferred_name.py

## CELTS - Update User Records
Schedule: **4am every day**
Location: **celts@celts-link**
Method: **cron**

Gets class and major data from Tracy and preferred name from LDAP to update user information. Runs https://github.com/BCStudentSoftwareDevTeam/celts/blob/production/app/scripts/import_users.py.

## Apache Restarts
Method: **cron**
User: **root**

Restart apache so MySQL doesn't die after a few days.

celts-link: **3:02am**
lsf: **3:03am**

