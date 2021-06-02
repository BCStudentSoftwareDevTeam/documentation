---
title: Linux 
description: 
published: true
date: 2021-06-02T15:06:50.601Z
tags: 
---

# Basic Linux Commands
If you are new to Linux, here are some basic commands to help you navigate the server. Most of these commands have additional arguments that alter their functionality. You can learn more about any unix command with the `man` utility. Example: access the `ls` man page with `man ls`. 

`ls`
Shows all the files in the directory.

`ls -al`
shows all files in the directory, including hidden files, and displays basic information about each file.

`cd <DIR>`
Changes the current directory.

`cd ..`
Changes to the parent directory.

`cd ~/`
Changes to your home directory.

`cp <SOURCE> <DESTINATION>`
Copies a file or directory.

`exit` or `ctrl-D`
Logs you out of your shell.

`touch <FILE>`
Creates file if filename doesn’t exist. Only updates its timestamp if it does.

`rm <FILE>`
Removes file.

`rm -r <DIRECTORY>`
Deletes a directory and everything in it (careful with this one).

`mkdir <DIRECTORY>`
Creates a directory.

`mv <SOURCE> <DESTINATION>` 
Moves a file to another location.

`find -name <SEARCH>`
Finds files whose names match the pattern. There are many, many options for the `find` command.

`man`
View the manual for a command. Example: `man cd`

`vim` or `nano`
Vim and Nano are text editors. Vim is much, much better for coding or heavy text editing, but harder to learn.

# Common Tasks


# Resources
If you want to learn about more commands, linux philosophy and how to navigate the OS, here are some additional resources:

https://files.fosswire.com/2007/08/fwunixref.pdf
https://www.linuxtrainingacademy.com/linux-commands-cheat-sheet/
https://www.techworm.net/2016/10/download-cheat-sheet-learn-basic-linux-commands.html

