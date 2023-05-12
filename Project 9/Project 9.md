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

![jenkins-setup2](./Images/jenkins-setup2.png)

# Step 2 – Configure Jenkins to retrieve source codes from GitHub using Webhooks

` Enable webhooks in your GitHub repository settings`

![jenkins-github-webhook](./Images/jenkins-github-webhook.png)

`Configure the new freestyle project and enable your first build`

![first-build-jenkins](./Images/first-build-jenkins.png)

![jenkins-console-output1](./Images/jenkins-console-output1.png)

# Click "Configure" your job/project and add these two configurations

`Configure triggering the job from GitHub webhook:`

`Configure "Post-build Actions" to archive all the files – files resulted from a build are called "artifacts".`

`Make an update in the repo and the build will trigger automatically`

![second-build-jenkins](./Images/second-build-jenkins.png)



