# LAMP

**L**inux **A**pache **M**ySQL **P**HP


## Contents

- [Linux](#linux)
- [Apache2](#apache)
- [MySQL](#mysql)
- [PHP](#php)

## Linux

Update the packages:
```bash
sudo apt update
sudo apt upgrade
```
---

## Apache

Install Apache 2

```bash
sudo apt install -y apache2
```
Check web traffic:
```bash
sudo ufw app list
# Available applications:
#   Apache
#   Apache Full
#   Apache Secure
#   ...
sudo ufw app info "Apache Full"
# Profile: Apache Full
# Title: Web Server (HTTP,HTTPS)
# Description: Apache v2 is the next generation of the omnipresent Apache web
# server.
#
# Ports:
#   80,443/tcp
```

If the responses are different enable `Apache Full`:

```bash
sudo ufw allow in "Apache Full"
```

The default Apache2 web page is available at:

http://127.0.0.1/ or http://localhost/

---
## MySQL

Install MySQL:

```bash
sudo apt install -y mysql-server
```

Launch the `mysql_secure_installation` script:

```bash
sudo mysql_secure_installation
```
- **VALIDATE PASSWORD PLUGIN** -> **Y**
  - `0 => LOW`: length >= 8
  - `1 => MEDIUM`: length >= 8, numeric, mixed case, special characters
  - `2 => STRONG`: length >= 8, numeric, mixed case, special characters, dictionary
- **Type root password**
- **Remove anonymous users** -> **Y**
- **Disallow root login remotely** -> **Y**
- **Remove test database and access to it** -> **Y**
- **Reload privilege tables now** -> **Y**

Change root password from MySQL shell:

```bash
sudo mysql
mysql> SELECT user, authentication_string, plugin, host from mysql.user;
# root has not authentication_string
ALTER USER `root`@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password';
mysql> FLUSH PRIVILEGES;
mysql> SELECT user, authentication_string, plugin, host from mysql.user;
# now root has authentication_string
mysql> quit
```
Now, generally after reboot, you can log into mysql with:
```bash
sudo mysql -p
# or
mysql -u root -p
```
---
## PHP

Install PHP and its plugins:

```bash
sudo apt install -y php libapache2-mod-php php-mysql
sudo apache2ctl restart
```

#### Check is it works

Create **info.php** file at `/var/www/html/`:

```html
<?php
phpinfo();
?>
```
got to http://127.0.0.1/info.php or http://localhost/info.php

if works remove it for security reasons.
