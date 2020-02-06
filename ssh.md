---
title: SSH - Secure Network Access
description: 
published: true
date: 2020-02-06T22:11:07.335Z
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

In Windows, you will need an application to start using SSH. [PuTTY](https://www.putty.org/) and [MobaXterm](http://mobaxterm.mobatek.net/download.html) are both popular - we will give instructions for MobaXterm, but the basics are the same for all SSH clients.

1. Download and start your client
2. In MobaXTerm, you can type the above ssh commands directly into their Home window. Setting up a session will let you save your configuration for next time.
3. Click the Session icon in MobaXterm and choose SSH
    ![mobaxterm-session-icon.png](/mobaxterm-session-icon.png)
4. Fill out the Basic SSH settings section:
    * **Remote Host:** Your VM’s IP address (given to you in the email)
    * **Username:** Your username (given to you in the email)
    * **Port:** 22
5. Click OK. You will now be able to select this session in the Sessions sidebar on the left whenever you need a new session.

*You can use whatever GUI client you wish - the settings will be the same.*

*You can avoid entering a password every time you connect by setting up public key auhentication. See below* ↓

## Public Key Authentication

Public/Private Key Authentication is a powerful authentication pattern that uses modern cryptography. Each user creates a pair of keys: a **private key** that is known only to the user, and a **public key** that is shared everywhere that a user needs to authenticate.

Many services use public key authentication to ensure that only authorized users are able to access their applications. [GitHub](https://github.com/settings/keys), Bitbucket, and many development tools have ways to authenticate without passwords by uploading your public keys to the application profile.

For SSH remote access, an `authorized_keys` file is maintained in `~/.ssh/` with all of the public keys that can access a server. Locally, the private keys are stored and referenced in ssh as identity keys. You can specify a specific identity key for a particular server when you are logging in (e.g., `ssh -i ~/.ssh/special-server-key myuser@special-server`), or you can configure this in your ssh configuration file, `~/.ssh/config`.

> Anyone who has your private key can impersonate you, just as anyone with your password can. Do not share your private key!
{.is-danger}


### Setup

If you have never created a keypair before on your device, you will need to do so now. Otherwise you can use your existing public and private keys. Run the following commands in a terminal application (MobaXterm works for Windows).

**Create a key:** `ssh-keygen`
You can choose the defaults to save the file in `~/.ssh/` and with no passphrase, or you can choose a passphrase if you want to require a password as well as use key authentication. If you aren't sure, don't use a passphrase.

**Copy ID to remote machine:** `ssh-copy-id USER@REMOTE_HOST`
By default this will copy the id_rsa public key to the remote user's `authorized_hosts` file. Use the `-i /path/to/identitykey` option if you wish to copy a different key.


### Windows Extras

If you want your MobaXterm (or PuTTY) sessions to use public key authentication, you will need to change the appropriate settings. For MobaXterm:

1. Open the Session settings
2. Click on the Advanced SSH setting tab located at the bottom: 
    * Check the 'Use private key' box.
    * Select your private key from above. 

For PuTTY, you will need to use pageant.exe, which comes with the PuTTY binary. [Here are instructions for using Pageant](https://www.digitalocean.com/community/tutorials/how-to-use-pageant-to-streamline-ssh-key-authentication-with-putty)

## Start an SSH Server
These steps are only necessary if you are wanting to be able to connect to your local computer from somewhere else.

### Linux Setup
In modern Ubuntu, run `sudo systemctl enable ssh` to enable it on startup, and `sudo systemctl start ssh` to start it immediately.

### Mac Setup
In your 'Sharing' pane in System Preferences, enable Remote Login. Then, choose 'Only these users' and add your user to the box with the '+' button.

### Windows Setup
Follow [this document](https://winscp.net/eng/docs/guide_windows_openssh_server). Good luck.

## Troubleshooting

### Debugging
The first step in troubleshooting SSH issues is to turn on debugging. You can enable increasing levels of debugging output with the `-v-`, `-vv`, and `-vvv` flags. Make another attempt with debugging turned on so you can see what part of the authentication protocol is failing.

### Permissions Error
A common error is that the permissions of the key files are bad. On Linux and Mac OS, this means that your `.ssh/` directory and your private key files should only be readable and writeable by you. You can change this with chmod: `chmod 600 your_key_file`.

### Password Prompts
If you are being prompted for a password even though you should be using a key, check that your public key is properly in the `~/.ssh/authorized_keys` file on the target machine. If it is, turn on debugging output to see if ssh is trying the right key for this server. Remember you can use `-i /path/to/keyfile` to use a different key for a connection.

## Further Reading


SSH Tunneling - Communicate using insecure protocols through a secure SSH connection
X-Forwarding - View graphical applications locally that run on a server
