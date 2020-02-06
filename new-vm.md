---
title: New Development VM
description: Using your new development virtual machine
published: true
date: 2020-02-06T03:48:32.954Z
tags: 
---

# Using your new virtual machine

A **virtual machine**, or VM, is an emulation of a computer system. Many different virtual machines can be hosted on one piece of computer hardware, but they each appear as their own individual computer system.

You will use an **IP address** to access this system, or, hopefully soon, a **hostname**. The IP address is a set of 4 numbers that uniquely identifies the computer on the network (e.g., 172.31.2.118), and the hostname is the human-readable name of the computer (e.g., test-dev).

These VMs run Ubuntu, a **Linux** distribution. Linux is the operating system that runs most of the worldwide web, as well as all Android phones, and many other types of computers. This VM uses Ubuntu Server, with no graphical interface, but there are many desktop versions of Linux as well. To learn more about using Linux, [click here](/linux).


## Login Credentials

You can access your VM with a username and password. The initial password is the same as your username (likely the same as your Berea College username - check your email), and you will be prompted to change it on your first login. A better way to access your VM is with [public key authentication for SSH](/ssh). A single key can access multiple VMs, and you will not have to enter your password every time you log in.

## Administrator Privileges

The super-user in Linux is called `root`. Some system operations and system log files require super-user permissions. You have the ability to perform these tasks by using the `sudo` command. Example: `sudo shutdown -r now` instead of `shutdown -r now`. See the [linux](/linux) page for more details. Also,
![sandwich.png](/sandwich.png)
https://xkcd.com/149/

## Personal Website

If you navigate to http://172.31.2.118/ in your browser, using your own IP address, you will see a website that is run from your new VM. You can edit this site to be whatever you want (nothing illegal, please) by changing the files in the `www/` directory inside your home directory. If you wanted to run it using Python or PHP (installed), or other server tech, you can find documentation out there for it.
*Note: Class-specific or application-specific virtual machines may have this functionality removed or altered*

## MySQL
## Python versions
## Flask applications
## Apache configuration
## Using Docker