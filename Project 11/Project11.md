## INSTALL AND CONFIGURE ANSIBLE ON EC2 INSTANCE

`1 - Update Name tag on your Jenkins EC2 Instance to Jenkins-Ansible. We will use this server to run playbooks.`

![Jenkins-Ansible-Server](./Images/Jenkins-Ansible-Server.png)

`2 - In your GitHub account create a new repository and name it ansible-config-mgt.`

![Github-repo](./Images/Github-repo.png)

`3 - Install Ansible`

`sudo apt update`

`sudo apt install ansible`

![Apt-Update](./Images/Apt-Update.png)

![Apt-Upgrade](./Images/Apt-Upgrade.png)

![Ansible-Installation](./Images/Ansible-Installation.png)

![Ansible-Version](./Images/Ansible-Version.png)

`4 - Configure Jenkins build job to save your repository content every time you change it – this will solidify your Jenkins configuration skills acquired in Project 9.`

![Ansible-Freestyle](./Images/Ansible-Freestyle.png)

![Jenkins-Git-Repo](./Images/Jenkins-Git-Repo.png)

![jenkins-webhook1](./Images/jenkins-webhook1.png)

`5 - Test your setup by making some change in README.MD file in master branch and make sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder`

![Autobuild-Jenkins-Github](./Images/Autobuild-Jenkins-Github.png)

`ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/`

![Jenkins-archive](./Images/Jenkins-archive.png)

![New-Jenkins-Setup](./Images/New-Jenkins-Setup.png)

`NB: Assign an Elastic IP Address to the Jenkins Server`

![Jenkins-ElasticIP](./Images/Jenkins-ElasticIP.png)

# Step 2 – Prepare your development environment using Visual Studio Code

![Ansible-VSC](./Images/Ansible-VSC.png)
# BEGIN ANSIBLE DEVELOPMENT

`1 - In your ansible-config-mgt GitHub repository, create a new branch that will be used for development of a new feature.`

`2 - Checkout the newly created feature branch to your local machine and start building your code and directory structure`

`3 - Create a directory and name it playbooks – it will be used to store all your playbook files.`

![Playbooks-folder](./Images/Playbooks-folder.png)

`4 - Create a directory and name it inventory – it will be used to keep your hosts organised.`

![Inventory-folder](./Images/Inventory-folder.png)

`5 - Within the playbooks folder, create your first playbook, and name it common.yml`

`6 - Within the inventory folder, create an inventory file (.yml) for each environment (Development, Staging Testing and Production) dev, staging, uat, and prod respectively.`

![playbooks-and-inventory-files](./Images/playbooks-and-inventory-files.png)

