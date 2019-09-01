# phpMyAdmin

## Contents
- [Requirements](#requirements)
- [Installation](#installation)


## Requirements
See **LAMP**

## Installation
```bash
sudo apt install -y phpmyadmin php-mbstring php-gettext
```
- chose **apache2**
- `dbconfig-common` -> **yes**
- enter password

add to `/etc/apache2/apache2.conf`:

```
Include /etc/phpmyadmin/apache.conf
```
Restart Apache2:
```bash
sudo apache2ctl restart
```
It is now available at http://127.0.0.1/phpmyadmin/ or http://localhost/phpmyadmin/
