---
title: New Development VM
description: Using your new development virtual machine
published: true
date: 2020-02-06T04:12:03.107Z
tags: 
---

# Using your new virtual machine

A **virtual machine**, or VM, is an emulation of a computer system. Many different virtual machines can be hosted on one piece of computer hardware, but they each appear as their own individual computer system.

You will use an **IP address** to access this system, or, hopefully soon, a **hostname**. The IP address is a set of 4 numbers that uniquely identifies the computer on the network (e.g., 172.31.2.118), and the hostname is the human-readable name of the computer (e.g., test-dev).

These VMs run Ubuntu, a **Linux** distribution. Linux is the operating system that runs most of the worldwide web, as well as all Android phones, and many other types of computers. This VM uses Ubuntu Server with a **command line interface (CLI)**, but there are many desktop versions of Linux as well. To learn more about using Linux, [click here](/linux).


## Login Credentials

You can access your VM with a username and password. The initial password is the same as your username (likely the same as your Berea College username - check your email), and you will be prompted to change it on your first login. A better way to access your VM is with [public key authentication for SSH](/ssh). A single key can access multiple VMs, and you will not have to enter your password every time you log in.

## Administrator Privileges

The super-user in Linux is called `root`. Some system operations and system log files require super-user permissions. You have the ability to perform these tasks by using the `sudo` command. Example: `sudo shutdown -r now` instead of `shutdown -r now`. See the [linux](/linux) page for more details. Also,
![sandwich.png](/sandwich.png)
https://xkcd.com/149/

## Personal Website

If you navigate to http://172.31.2.118/ in your browser, using your own IP address, you will see a website that is run from your new VM. You can edit this site to be whatever you want (nothing illegal, please) by changing the files in the `www/` directory inside your home directory. If you wanted to run it using Python or PHP (installed), or other server tech, you can find documentation out there for it.
*Note: Class-specific or application-specific virtual machines may have this functionality removed or altered.*

## MySQL

Your VM has the database engine MySQL installed. You can access it from the command line using the `mysql` command, or using [phpMyAdmin](https://www.phpmyadmin.net/docs/) at http://172.31.2.118/phpmyadmin. By default you can access the database with the user *root* and password *root*, and from there you can create any other users and databases you need for your work, either through the CLI or phpmyadmin. Example: `mysql -u root -proot`. Read the [database](/database) documentation for more information.

## Python versions

Both Python versions 2 and 3 are installed on your machine, with Python 3 set as the default. You may have to work on a project that requires you to use python 2, but **you should not use python 2 for new projects.** See our [Python](/python) documentation for more details about setting up virtual environments and general Python usage.

## Flask applications
Blurb coming soon. [Flask](/flask)

## Apache configuration
Blurb coming soon. [Apache](/apache)

## Docker

Blurb coming soon. [Docker](/docker)