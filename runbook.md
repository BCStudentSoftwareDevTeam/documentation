---
title: Runbooks
description: Common system administration tasks
published: true
date: 2024-01-11T19:57:26.493Z
tags: 
editor: markdown
dateCreated: 2023-03-10T15:23:20.283Z
---

## Common Requests

### User Management
"User/instructor/student X is not in system Y"

| Application | LDAP | Ultratime | Preferred Name | Script                      |  |
|-------------|------|-----------|----------------|:----------------------------|----------|
| BCSR        | X    | X         | X              | `add_user.py`                 | [details](/runbook/new-bcsr-user) 
| URCPP       | Y    | X         | X              | `sync_faculty.py`             | [details](/runbook/new-urcpp-user)
| CELTS       | Y    | Y         | Y              | `app/scripts/import_users.py` | [details](/runbook/celts-users)
| CAS         | Y    | X         | X              | `sync_faculty.py`             | [details](/runbook/new-cas-user)
| LSF         | Y    | Y         | Y              | `scripts/app/*.py`            | [details](/runbook/lsf-users)
| Chemical    | X    | X         | N/A            | N/A                           | [details](/runbook/new-chemical-user)

### BCSR
- [Add a new instructor](/runbook/new-bcsr-user)
- [Add courses for upcoming term](/runbook/add-term)

## Creating Servers
* [New Docker Application](/runbook/new-docker-server)

## Upgrading Servers
* [Upgrade Jenkins](/runbook/upgrade-jenkins)
* [Upgrade wiki documentation](/runbook/upgrade-wiki)