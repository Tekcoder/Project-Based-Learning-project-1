## CONFIGURE APACHE AS A LOAD BALANCER

`1 - Create an Ubuntu Server 20.04 EC2 instance and name it Project-8-apache-lb, so your EC2 list will look like this`

![ApacheServer](./Images/ApacheServer.png)

# Install Apache Load Balancer on Project-8-apache-lb server and configure it to point traffic coming to LB to both Web Servers:

`#Install apache2`

`sudo apt update -y && sudo apt upgrade -y`

`sudo apt install apache2 -y`

`sudo apt-get install libxml2-dev`

`#Enable following modules:`

`sudo a2enmod rewrite`

`sudo a2enmod proxy`

`sudo a2enmod proxy_balancer`

`sudo a2enmod proxy_http`

`sudo a2enmod headers`

`sudo a2enmod lbmethod_bytraffic`

`#Restart apache2 service`

`sudo systemctl restart apache2`

![installing-apache-load-balancer](./Images/installing-apache-load-balancer.png)