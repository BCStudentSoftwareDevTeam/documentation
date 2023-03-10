---
title: Upgrade Wiki Documentation
description: 
published: true
date: 2023-03-10T15:57:22.072Z
tags: 
editor: markdown
dateCreated: 2023-03-10T15:57:22.072Z
---

# Upgrade Wiki Docs

Our documentation wiki uses wiki.js, running in Docker, so upgrading is simple (theoretically).

1. SSH as root to the documentation VM: ssdt-documentation.berea.edu
2. Make sure that the wiki content backup is working: https://github.com/BCStudentSoftwareDevTeam/documentation
1. Update the wiki and postgres images to the latest major version
`docker-compose pull`
2. Stop the running containers
`docker-compose stop`
4. Remove the old container
`docker-compose rm`
5. Recreate the container in daemon mode
`docker-compose up -d`

### Resources:
* https://docs.requarks.io/install/upgrade