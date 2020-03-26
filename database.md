---
title: Databases
description: 
published: true
date: 2020-03-26T11:16:36.826Z
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
TBD

### Recovering Root Access

If you have root access to your computer but do not have the mysql root password anymore, you can reset it.

1. Stop your running mysql server with `systemctl stop mysql`.
2. Create missing directory, fix permisisons: `mkdir /var/run/mysqld; chown mysql:adm /var/run/mysqld`
3. Switch to the mysql user: `su - mysql -s /bin/bash`
4. Start the server in safe mode: `mysqld_safe --skip-grant-tables --skip-networking &`
5. Connect to the server with `mysql -u root`.
6. Reset the password:
    
    mysql> use mysql;
    mysql> UPDATE user SET authentication_string=password('root') WHERE user='root';
    mysql> FLUSH PRIVILEGES;



## PostgreSQL
TBD
## MongoDB
TBD