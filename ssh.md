---
title: SSH - Secure Network Access
description: 
published: true
date: 2020-02-06T19:49:09.339Z
tags: 
---

## What is SSH?

**SSH**, or Secure Shell, is a network protocol and suite of tools that enable secure communication over an untrusted network. We use SSH to connect to our physical and virtual computers

## Remote Access Using SSH

There are two endpoints for the SSH protocol, the **client** and the **server**. The computer you are connecting to must be running an SSH server, and the computer (whether laptop, phone, desktop, or virtual machine) you are using to connect must use an ssh client. If you are running an ssh server locally, the simplest connection using ssh is to your own computer: `ssh localhost`. This is a good way to test if your ssh client and server are working.

If you are just trying to connect to a remote server, use your ssh client and specify the user and machine to which you are connecting. Example: `ssh ramsayb2@172.31.3.69` or `ssh wiki@documentation.ssdt.berea.edu`. If you do not specify a user, your current username will be used. You will be prompted for a password, if password authentication is enabled on the server and you are not using a public/private keypair.

### Linux / Mac OS Setup

SSH is available by default on these operating systems. You will need to open a terminal window to access the command line. For Linux use whatever your distribution provides, on a Mac use Terminal or download [iTerm 2](https://iterm2.com/). Then, enter your ssh command as shown in the examples above: `ssh USER@TARGET_COMPUTER`.

### Windows Setup

In Windows, you will need an application to start using SSH. [PuTTY](https://www.putty.org/) and [MobaXTerm](http://mobaxterm.mobatek.net/download.html) are both popular - we will give instructions for MobaXTerm, but the basics are the same for all SSH clients.

1. Download and start your client
2. In MobaXTerm, you can type the above ssh commands directly into their Home window. Setting up a session will let you save your configuration for next time.
3. Click the Session icon in MobaXTerm and choose SSH
    ![mobaxterm-session-icon.png](/mobaxterm-session-icon.png)
4. Fill out the Basic SSH settings section:
    * **Remote Host:** Your VM’s IP address (given to you in the email)
    * **Username:** Your username (given to you in the email)
    * **Port:** 22
5. Click OK. You will now be able to select this session in the Sessions sidebar on the left whenever you need a new session.

*You can use whatever GUI client you wish - the settings will be the same.*

## Public Key Authentication

### Linux / Mac OS Setup

### Windows Setup

## Start SSH Server

### Linux Setup

### Mac Setup

### Windows Setup

## Further Reading


SSH Tunneling - Communicate using insecure protocols through a secure SSH connection
X-Forwarding - View graphical applications locally that run on a server
