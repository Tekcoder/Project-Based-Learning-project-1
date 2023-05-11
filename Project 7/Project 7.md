## DEVOPS TOOLING WEBSITE SOLUTION

# DevOps Tooling Solution that will consist of:

# 1- Jenkins – free and open source automation server used to build CI/CD pipelines.

# 2 - Kubernetes – an open-source container-orchestration system for automating computer application deployment, scaling, and management.

# 3 - Jfrog Artifactory – Universal Repository Manager supporting all major packaging formats, build tools and CI servers. (Artifactory).

# 4 - Rancher – an open source software platform that enables organizations to run and manage Docker and Kubernetes in production.

# 5 - Grafana – a multi-platform open source analytics and interactive visualization web application.

# 6 - Prometheus – An open-source monitoring system with a dimensional data model, flexible query language, efficient time series database and modern alerting approach.

# 7 - Kibana – Kibana is a free and open user interface that lets you visualize your Elasticsearch data and navigate the Elastic Stack.

## Components of the Infrastructure 

# 1 - Webserver Linux: Red Hat Enterprise Linux 8

# 2 - Database Server: Ubuntu 20.04 + MySQL

# 3 - Storage Server: Red Hat Enterprise Linux 8 + NFS Server

![Three-Tier-Architecture](./Images/3-tier-Application-Infrastructure.jpg)

# NB: The RHEL 8 isn't available in the general AMI, you go to the public images and search for RHEL-8.6.0_HVM-20220503-x86_64-2-Hourly2-GP2

![Public-AMIs](./Images/Public-AMIs.png)

# Step 1 – Prepare NFS Server

![NFS-Server](./Images/NFS-Server.png)

# Create 3 EBS Volumes and attach to the NFS Server

![AttachedEBSVolumes](./Images/AttachedEBSVolumes.png)

# Create 3 Logical Volumes: lv-opt lv-apps, and lv-logs

`lsblk`

![Available Disks and Partitions](./Images/Available%20Disks%20and%20Partitions.png)

# Physical Volumes | Volume Group | Logical Volumes

![Creation-of-Physical-Volumes-Volume-Group-Logical-Volume](./Images/Creation-of-Physical-Volumes-Volume-Group-Logical-Volume.png)

# Use mkfs.xfs to format the logical volumes with xfs filesystem

`sudo mkfs.xfs /dev/nfs-vg/lv-apps`

`sudo mkfs.xfs /dev/nfs-vg/lv-logs`

`sudo mkfs.xfs /dev/nfs-vg/lv-opt`

![Formating the logical volumes](./Images/Formating%20the%20logical%20volumes.png)

# Create /mnt/apps directory to store website files

# Create /mnt/log to store backup of log data

# Create /mnt/opt for the Jenkins Server

![Mount-points-on-the-NFS-Server](./Images/Mount-points-on-the-NFS-Server.png)

# Mount /mnt/apps on lv-apps logical volume

![NFS-Folders-Mounted-on-the-Logical-Volumes](./Images/NFS-Folders-Mounted-on-the-Logical-Volumes.png)

# Install NFS server

# Make sure we set up permission that will allow our Web servers to read, write and execute files on NFS:

![Mount-points-ownership](./Images/Mount-points-ownership.png)

# Configure access to NFS for clients within the same subnet (example of Subnet CIDR – 172.31.32.0/20 ):

![Configure-NFS-Server-Access-To-Web-Servers](./Images/Configure-NFS-Server-Access-To-Web-Servers.png)

![Configure-NFS-Server-Access-To-Web-Servers B](./Images/Configure-NFS-Server-Access-To-Web-Servers%20B.png)

# Check which port is used by NFS and open it using Security Groups (add new Inbound Rule)

`rpcinfo -p | grep nfs`

![nfs-server-ports](./Images/nfs-server-ports.png)

# NFS Ports opened in the Security Group

![nfs-server-security-group](./Images/nfs-server-security-group.png)

# STEP 2 — CONFIGURE THE DATABASE SERVER

![Database-Server-and-Web-Servers](./Images/Database-Server-and-Web-Servers.png)

# Install MySQL server

![MySql-Server-Installation](./Images/MySql-Server-Installation.png)