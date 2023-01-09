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