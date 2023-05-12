## TOOLING WEBSITE DEPLOYMENT AUTOMATION WITH CONTINUOUS INTEGRATION. INTRODUCTION TO JENKINS

# Task
`Enhance the architecture prepared in Project 8 by adding a Jenkins server, configure a job to automatically deploy source codes changes from Git to NFS server.`

`Here is how your updated architecture will look like upon competion of this project:`

![Project9-Architecture](./Images/Project9-Architecture.png)

# INSTALL AND CONFIGURE JENKINS SERVER

`Step 1 – Install Jenkins server`

`1 - Create an AWS EC2 server based on Ubuntu Server 20.04 LTS and name it "Jenkins"`

![Jenkins-Server](./Images/Jenkins-Server.png)

`2 - Install JDK (since Jenkins is a Java-based application)`

`sudo apt update -y && sudo apt upgrade -y`

`sudo apt install openjdk-11-jre`

`java -version`


`3 - Install Jenkins`

`curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \`
  `/usr/share/keyrings/jenkins-keyring.asc > /dev/null`
`echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \`
  `https://pkg.jenkins.io/debian binary/ | sudo tee \`
  `/etc/apt/sources.list.d/jenkins.list > /dev/null`
`sudo apt-get update`
`sudo apt-get install jenkins`

`sudo systemctl status jenkins`

`4 - Perform initial Jenkins setup`

![jenkins-setup](./Images/jenkins-setup.png)