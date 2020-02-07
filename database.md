---
title: Databases
description: 
published: true
date: 2020-02-07T14:19:53.408Z
tags: 
---

# Database
Your content here

# SQL

# Specific Engines

## MySQL / MariaDB
MySQL and MariaDB are open source database implementations that are fully compatible with each other. MariaDB is a fork of the MySQL project, and is a drop-in replacement. The commands even still use the mysql name.

### Installing
TBD

### Default username and password

By default, the mysql root user has no password, but is only accessible when your host user is the superuser (root). This means that this command, `mysql -u root`, will not work out of the box as your normal user. You would need to use sudo, like `sudo mysql -u root`. It is generally not good to have an unsecured root login anywhere, but if you are setting this up in a development environment it is probably ok. To change the user so you can access it without sudo, connect to mysql and run the following SQL:

    mysql> DROP USER 'root'@'localhost';
    mysql> CREATE USER 'root'@'%' IDENTIFIED BY '<PASS>';
    mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
    mysql> FLUSH PRIVILEGES;

Replace \<PASS> with the password you want, or with nothing for an empty password.

### Using

## PostgreSQL

## MongoDB