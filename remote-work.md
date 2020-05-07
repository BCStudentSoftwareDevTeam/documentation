---
title: Remote Work
description: 
published: true
date: 2020-05-07T19:17:56.779Z
tags: 
---

## Communication
Talk to people!

## Health
Take breaks!

## Technical

### VPN
You will need to be connected to Berea's VPN to connect to any of our development servers. You will need to fill out the VPN Request form. Since the VPN is required to use view this wiki, you likely are already connected.

If you are set up for local development, you can avoid using a VPN. 

### Collaborative Editing

#### Atom + Teletype

The editor [Atom](atom.io) has a plugin called [Teletype](https://teletype.atom.io/) that enables collaboration on individual files. It requires a GitHub login to work. 

Once you have installed the plugin:
* Click the teletype radio tower icon in the bottom right of your editor
* Sign in using GitHub if you have not done so.
* To share, click the share button and copy the shared portal invite URL, and give it to your collaborators.
* To join, click Join and enter the shared invite URL you have been given.

This will share your active tab among collaborators.

#### Vim + Screen

[GNU Screen](https://linuxize.com/post/how-to-use-linux-screen/) is a built-in tool on unix systems for opening multiple virtual terminals within a single session (terminal multiplexing). A screen session will persist after you disconnect from a server, and can be shared between multiple users. See our [screen documentation](/screen) for basic screen usage. Once in screen you can create new terminals, edit with [vim](/vim), and do any other task you would do in a local terminal or over SSH.

* Share a screen session with other users:  `Ctrl-a :multiuser on`.
* Add a user to your screen session: `Ctrl-a :acladd username`.
* Connect to someone else's shared screen: `screen -x otheruser/sessionname`.

The screen session will persist after you disconnect (`Ctrl-a d`) and can be reconnected to at any time unless the server has been restarted.



