---
title: Virtual Machine Management
description: Creating, Maintaining, and Destroying Virtual Machines
published: true
date: 2022-09-14T19:13:16.966Z
tags: infra
editor: markdown
dateCreated: 2021-06-02T14:47:57.713Z
---

# Common Tasks

## Resizing a VM disk
Sometimes the initial size of a VM's storage was too small and it is necessary to increase it. If we host the virtual machine we can resize it ourselves. Production applications will require IS&S involvement to add more space. 

If the partition table uses logical partitions inside an Extended partition (partition number starts with 5 or higher - e.g., `/dev/sda5`), you cannot use `virt-resize`. Unfortunately, this is how the Ubuntu 20.04 image from `virt-builder` is set up, so partitions on those machines have to be resized manually.

This is an example partition table that `virt-resize` **CAN** expand:

    Device     Boot Start      End  Sectors Size Id Type
    /dev/vda1  *     2048 12580863 12578816   6G 83 Linux

This is an example partition table that `virt-resize` **CANNOT** expand:

    Device     Boot   Start      End  Sectors  Size Id Type
    /dev/vda1  *       2048  1050623  1048576  512M  b W95 FAT32
    /dev/vda2       1050624 41943039 40892416 19.5G  5 Extended
    /dev/vda5       1050626 41943039 40892414 19.5G 83 Linux


### Viewing the partitions in a disk image
You can get a view into the disk image without booting the VM with `virt-filesystems`:

    root@fee:/vm/vm0# virt-filesystems --partitions --long -a seedMain.img
    Name       Type       MBR  Size         Parent
    /dev/sda1  partition  0b   536870912    /dev/sda
    /dev/sda2  partition  05   1024         /dev/sda
    /dev/sda5  partition  83   20936915968  /dev/sda

### Using virt-resize
1. Create a new image with the desired size in the qcow2 format:  `qemu-img create -f qcow2 -o preallocation=metadata newdisk.img 20G`
2. Resize the old image into the new image, expanding the given partition to fill the new space: `virt-resize --expand /dev/sda2 olddisk.img newdisk.img`
3. Rename the old image (for backup purposes) and rename the new image to replace the old one.
4. Boot the virtual machine - it may take awhile the first time


### Using fdisk
1. Create a new image with the desired size in the qcow2 format:  `qemu-img create -f qcow2 -o preallocation=metadata newdisk.img 20G`
2. Copy the old image into the new image. The partitions will be the same size. `virt-resize olddisk.img newdisk.img`
3. Rename the old image (for backup purposes) and rename the new image to replace the old one.
4. Boot into the VM
5. To resize without rebooting, follow the steps in https://medium.com/100-days-of-linux/how-to-resize-a-linux-root-file-system-af3e5096b4e4
    a. Using `fdisk`, delete and recreate the main filesystem partition (the Extended and Linux partition)
    b. Make sure the starting sector of the new Linux partition matches the old one. You may need to adjust the starting sector of the new partition in expert mode so that it matches the starting sector of the old partition. https://unix.stackexchange.com/a/320447
    c. Use `partprobe` to reload the partition table
    d. Resize the filesystem in the new partition to use the new available space
7. Reboot the virtual machine - it may take awhile the first time. Cross your fingers.


**References**
[virt-resize man page with examples](https://libguestfs.org/virt-resize.1.html)
[Resize Linux Root Filesystem](https://medium.com/100-days-of-linux/how-to-resize-a-linux-root-file-system-af3e5096b4e4)
[Extend Logical Partition inside Extended Partition](https://unix.stackexchange.com/a/320447)
[virt-filesystems man page](https://libguestfs.org/virt-filesystems.1.html)
[Red Hat virt-resize guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_deployment_and_administration_guide/sect-guest_virtual_machine_disk_access_with_offline_tools-virt_resize_resizing_guest_virtual_machines_offline)

