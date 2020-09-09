---
title: Collective Access
description: Applications based on the open-source Collective Access application
published: true
date: 2020-09-09T18:14:00.773Z
tags: php
---

# Collective Access

Installation guide (rough version):

## Server setup:
1. (optional) Install phpmyadmin: sudo apt-get install phpmyadmin. 
1.a. Requires adding “Include /etc/phpmyadmin/apache.conf” to /etc/apache2/apache2.conf
2. Install mysql: sudo apt-get install mysql-server
2.a. Put a password on the root account for MySQL: http://ssdt-documentation.berea.edu/database
3. Uninstall php7.2: sudo apt-get purge php7.2 (likely unnecessary now that CA 1.7.8 is installed)
4. Install php7.1: sudo apt-get install php7.1(likely unnecessary now that CA 1.7.8 is installed)
5. Install php mysql support: sudo apt install php-mysql
6. Install libcurl4 (uninstalls shib2 stuff, but that’s gonna be okay…): sudo apt-get install libcurl4
7. Install curl: sudo apt-get install curl
8. Install php-curl: sudo apt-get install php-curl
9. Install Ziparchive: sudo apt-get install php-zip
10. Install ntp (for time skew problem in shib: sudo apt-get install ntp
10.a. Fix the server’s timezone: sudo dpkg-reconfigure tzdata

## Migrate the db:
1. Export full db from old server. I prefer through phpmyadmin.
2. Import full db to new server. It’s likely large if it’s ljacatc/bcac, so I recommend doing the import itself via mysql commands on CLI: 
2.a. create the database in MySQL (phpmyadmin)
2.b. From CLI: mysql -u username -p new_database < data-dump.sql 

## Migrate the application code:
1. tar the directory of the application on the old server: sudo tar -czvf ca.tar.gz providence/
2. Export the tar to the new server: 
2.a. (from source) sudo scp <filename> <username>@<hostname_or_ip>:<remote_dir>
2.b. OR (from destination) sudo scp <username>:<hostname_or_ip>:<remote_file_to_copy>
3. Untar the file on the new server
4. Fix permissions problems.
  4.a. Everything needs readable by apache (i.e., www-data)
  4.b. **media/**, **app/tmp/** and **ezyang/htmlpurifier/library/HTMLPurifier/DefinitionCache/Serializer/** directories need to be readable and writeable by the web server.
4. Update setup.php with db connection info, app name, etc… 
5. Do database update suggested when you open CA in browser using “click here’ button, if upgrading versions
6. Move logo images to /themes/default/graphics/logos (set path to images in app.conf)

## Certs and Authentication 
1. Install certbot and https the application: https://certbot.eff.org/lets-encrypt/ubuntubionic-apache
2. Setup shibboleth3: https://www.switch.ch/aai/guides/sp/installation/?os=ubuntu18
2.a. If you get package problems because of shib2, do this:
  ```
  sudo apt-get install -f
  sudo dpkg --configure -a
  sudo apt-get install -f 
  ```


 