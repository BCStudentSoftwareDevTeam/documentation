---
title: Creating a Local Development Environment
description: 
published: true
date: 2020-06-30T16:08:22.086Z
tags: 
---

It can be simpler and faster to develop locally on your computer rather than on a remote server. While you will eventually need to test in a production-like environment, you won't always have to be connected to the VPN or deal with SSH disconnects and delay.

## Linux & Mac OS
On a linux machine, you will need to install the necessary dependencies with `apt` or other package manager, and then everything should be the same as the linux VMs.

Mac OS is Unix based, so the applications have a pretty good chance of working without modification, once you get the dependencies installed.

### Install Homebrew

**Mac OS only.**
Install Homebrew by following the instructions at [brew.sh](https://brew.sh/).


### Install & Configure Application Dependencies
You will need to install the necessary packages for your application. Included here are two common ones, Python 3 and MySQL.

**Mac OS**

- `brew install mysql` - if you are prompted for a root password, enter the necessary one for the application. E.g., for LSF it is 'root'. Otherwise, accept defaults.
- `brew tap homebrew/services`
- `brew services start mysql`
- `brew install python3`
- `brew install pip3`
- `ln -s /usr/local/bin/python3 /usr/local/bin/python`
- `ln -s /usr/local/bin/pip3 /usr/local/bin/pip`

**Ubuntu**

- `sudo apt install mysql-server` - if you are prompted for a root password, enter the necessary one for the application. E.g., for LSF it is 'root'. Otherwise, accept defaults.
- `sudo systemctl start mysql`
- `sudo systemctl enable mysql`
- `sudo mysql_secure_installation utility` - if you were unable to change the password on install, run this command.

**Ubuntu pre-18.04 needs python3 also**
- `sudo apt install python3`
- `sudo apt install python3-pip`


### Clone the application repository

Create an [SSH](/ssh) key for your local machine (or use one from `.ssh/` that is already created). Add the key to your bitbucket profile and use `git clone` to get the application code. Make sure you are using the `git+ssh` url, not `http` or `https`.

Follow your repository README to set up the application properly.



## Windows
You're on your own.