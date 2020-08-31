---
title: Databases
description: 
published: true
date: 2020-08-31T16:33:49.462Z
tags: 
---

# Database
Your content here

# SQL

# Specific Engines

## MySQL / MariaDB
MySQL and MariaDB are open source database implementations that are fully compatible with each other. MariaDB is a fork of the MySQL project, and is a drop-in replacement. The commands even still use the mysql name.

### Installing

Dev VMs should have mysql installed already. Should you need to, you can install the package `mysql-server` with apt: `sudo apt install mysql-server`.

To access the database with a programming language you will likely need to install a package with the database driver, e.g., `python3-mysqldb`.

If you want a graphical interface to your database, install the package `phpmyadmin`.

### Default username and password

By default, the mysql root user has no password and is only accessible when your host user is the superuser (root). This means that this command, `mysql -u root`, will not work out of the box as your normal user. You would need to use sudo, like `sudo mysql -u root`. It is generally not good to have an unsecured root login anywhere, but if you are setting this up in a development environment it is probably ok. To change the user so you can access it without sudo, connect to mysql and run the following SQL:

    mysql> DROP USER 'root'@'localhost';
    mysql> CREATE USER 'root'@'%' IDENTIFIED BY '<PASS>';
    mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
    mysql> FLUSH PRIVILEGES;

Replace \<PASS> with the password you want, or with nothing for an empty password.

### Using
https://dev.mysql.com/doc/mysql-getting-started/en/#mysql-getting-started-basic-ops

### Backing Up and Restoring
To back up a database, dump all of data and objects to a sql file.
`mysqldump -u root -p database_name > db_backup.sql`

To restore, create the new database and import the sql file.:

    mysql -u root -p -e 'CREATE DATABASE database_name'
    mysql -u root -p database_name < db_backup.sql

### Recovering Root Access

If you have root access to your computer but do not have the mysql root password anymore, you can reset it.

1. Stop your running mysql server with `systemctl stop mysql`.
2. Create missing directory, fix permissions: `mkdir /var/run/mysqld; chown mysql:adm /var/run/mysqld`
3. Switch to the mysql user: `su - mysql -s /bin/bash`
4. Start the server in safe mode: `mysqld_safe --skip-grant-tables --skip-networking &`
5. Connect to the server with `mysql -u root`.
6. Reset the password:

At the mysql prompt:
   
    mysql> use mysql;
    mysql> UPDATE user SET authentication_string=password('root') WHERE user='root';
    mysql> FLUSH PRIVILEGES;

7. Exit mysql and stop the existing server: `killall mysqld`
8. As root, restart mysql properly: `systemctl restart mysqld`

## Microsoft SQL Server

Accessing a SQL Server instance from linux requires an extra level of misdirection, FreeTDS.

1. Install the necessary packages:
`sudo apt-get install build-essential libssl-dev libffi-dev python3-dev python3.7-dev freetds-dev freetds-bin unixodbc-dev tdsodbc`
2. Edit `/etc/odbcinst.ini` according to https://gist.github.com/rduplain/1293636
3. Set up the connection for your language. For examples of doing it with pyodbc, SQLAlchemy, and Flask-SQLAlchemy, check out `db_test.py` in the LSF repo: https://bitbucket.org/laborstudents/lsf-flask/src/development/db_test.py 

## Oracle

### Client
To access an existing Oracle database from Ubuntu, you will need to install Oracle instantclient. There is a playbook in the [ansible repo](https://bitbucket.org/laborstudents/ansible_proj/src/master/) that can do this for you. Assuming you are set up to run ansible, run `ansible-playbook --private-key /PATH/TO/PRIVKEY -i SERVER, oracle_client.yml`. Of course, the private key does not have to be specified if ssh knows to use it by default. You may need to use `sudo`, depending on how ansible is set up.

For access from Python, you will also need to install [cx_Oracle](https://cx-oracle.readthedocs.io/en/latest/), `pip install cx_Oracle`.

### Server
TBD

## PostgreSQL
TBD
## MongoDB
TBD