---
title: Runbook - Upgrade Jenkins
description: 
published: true
date: 2023-03-08T21:54:10.032Z
tags: 
editor: markdown
dateCreated: 2023-03-08T21:26:30.475Z
---

# Upgrade Jenkins

Our Jenkins install uses Docker, so upgrading is simple (theoretically).

1. SSH as root to the jenkins VM: 172.31.3.151
1. Update the jenkins image to the latest major version
`docker pull bitnami/jenkins:2`
2. Stop the running container
`docker-compose stop jenkins`
3. Follow the backup steps
https://hub.docker.com/r/bitnami/jenkins/#backing-up-your-container
4. Remove the old container
`docker-compose rm -v jenkins`
5. Recreate the container in daemon mode
`docker-compose up -d`

### Resources:
* https://hub.docker.com/r/bitnami/jenkins/