# Apache 2

## Contents

- [Installation](#installation)
- [Management](#management)
- [User Dir](#user_dir)
- [URL Rewrite](#uer_rewrite)
- [Use PHP5](#use_php5)

## Installation

```bash
$ sudo apt install -y apache2
```

---

## Management

#### restart, stop, start

```bash
$ sudo apache2ctl [restart|stop|start]
# or
$ sudo systemctl [restart|stop|start] apache2
```
#### mod, site, conf
```bash
# mpd
$ sudo a2enmod <mod>
$ sudo a2dismod <mod>
# site
$ sudo a2ensite <site>
$ sudo a2dissite <site>
# conf
$ sudo a2enconf <conf>
$ sudo a2disconf <conf>
```
---

## User Dir

`UserDir` mod allows users to build a site in a folder of their home.

Edit `/etc/apache2/mods-available/userdir.conf`:

```
<IfModule mod_userdir.c>
	UserDir public_html
	UserDir disabled root

	<Directory /home/*/public_html>
		AllowOverride FileInfo AuthConfig Limit Indexes
		Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
		Require method GET POST OPTIONS
	</Directory>
</IfModule>
```
Change `public_html` with your desired folder and create that folder in your home.

Restart Apache2, see **Management**.

Now the site is available at http://127.0.0.1/~user_name/ or http://localhost/~user_name/

if you want allow only a specific user, you can replace `*` in `/home/*/public_html` with the `user_name`.

---

## URL Rewrite

TBD

---

## Use PHP5

Please use only if necessary.

```bash
# add ssh key
sudo add-apt-repository -y ppa:ondrej/php

# update
sudo apt update

# install php 5
sudo apt install -y php5.6 libapache2-mod-php5.6 php5.6-mysql php5.6-mbstring

# disable php 7
sudo a2dismod php7.2

# enable php 5
sudo a2enmod php5.6
```
