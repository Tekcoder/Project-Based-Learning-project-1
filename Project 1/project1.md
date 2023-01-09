## Awesome documentation for project 1 - Deploying a PHP MYSQL Application on Apache2 Server using Ubuntu 20.04 OS

![Project Infrastructure](./images/Project-1.jpg)

`sudo apt update`

![Server Update](./images/sudo-apt-update.png)

`sudo apt install apache2`

![Apache Server Installation](./images/sudo%20apt-install%20apache.png)

`sudo systemctl status apache2`

![Apache status](./images/sudo%20status%20apache.png)

`sudo apt install mysql-server`

![MySqL Installation](./images/mysql%20server%20install.png)

`sudo mysql`

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

![MySqL Login](./images/mysql%20login.png)

![MySqL Password](./images/mysql%20password.png)


`sudo apt install php libapache2-mod-php php-mysql`

![PHP Installation](./images/php%20installation.png)

`sudo mkdir /var/www/projectlamp`

`sudo chown -R $USER:$USER /var/www/projectlamp`

![PHP Folder](./images/folder%20user%20ownership.png)

`sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4 > /var/www/projectlamp/index.html`

![Index.html page](./images/index.html%20page.png)

`sudo vim /etc/apache2/mods-enabled/dir.conf`

### Change the Order of index.html and index.php

`sudo vim /etc/apache2/mods-enabled/dir.conf`

### Change this
`<IfModule mod_dir.c>`
        `DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm`
`</IfModule>`

`<IfModule mod_dir.c>`
        `DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm`
`</IfModule>`

`vim /var/www/projectlamp/index.php`

### Put this into index.php file

`<?php`
`phpinfo();`

`sudo systemctl reload apache2`

![PHP Index.php page](./images/index.php.png)