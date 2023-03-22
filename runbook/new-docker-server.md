---
title: Creating a Docker Application
description: 
published: true
date: 2023-03-22T17:31:06.398Z
tags: 
editor: markdown
dateCreated: 2023-03-10T17:32:33.243Z
---

# New Docker Server

In order to create a docker server you should have a `docker-compose.yml` file that sets up the docker containers for the application. If you want to persist data all the way to the host server so that if the VM is recreated the application data is retained, we need to create volumes on the hypervisor that we can mount in the VM.

These instructions operate from a branch of the [ansible_proj](https://github.com/BCStudentSoftwareDevTeam/ansible_proj/tree/create-base-vms) repo. The root directory is `brian/`, for now.

**Incomplete**: The creation and usage of volumes to persist data is not detailed here.

### Creating host volumes on host server (if needed)
1. If 4GB is enough, copy the blank volume to a new location
`cp /var/lib/libvirt/volumes/blank.img /var/lib/libvirt/volumes/data-persist.img`
If it is not enough, you will need to create a new volume to use: [Creating Volumes](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/virtualization_administration_guide/sect-virtualization-virtualized_block_devices-adding_storage_devices_to_guests)
2. Get the uuid of the new volume(s) (for later)

### Ansible Prep
1. Create a file in `vm/app_config/` with your application configuration. The name of the file corresponds to APP_TYPE used by the creation script. See `vm/app_config/wikijs.yml` for an example.
2. Create a docker-compose file for your application that will be copied to the new VM. The name of the directory corresponds to APP_TYPE used by the creation script. See `files/wikijs/` for an example.

### Server Creation
1. From the `tools/` directory, run the creation script
`./create_new_docker_app.sh APP_TYPE VM_NAME [local|staging|production]`

### Resources
- Creating Volumes:  https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/virtualization_administration_guide/sect-virtualization-virtualized_block_devices-adding_storage_devices_to_guests
- `docker-compose` info: https://www.simplilearn.com/tutorials/docker-tutorial/docker-compose