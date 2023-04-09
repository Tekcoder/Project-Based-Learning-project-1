## WEB SOLUTION WITH WORDPRESS

# Three-tier Architecture is a client-server software architecture pattern that comprise of 3 separate layers.

# Presentation Layer (PL): This is the user interface such as the client server or browser on your laptop.
# Business Layer (BL): This is the backend program that implements business logic. Application or Webserver
# Data Access or Management Layer (DAL): This is the layer for computer data storage and data access. Database Server or File System Server such as FTP server, or NFS Server

![Three-Tier Architecture](./images/three-tier-architecture.jpg)

# Your 3-Tier Setup

# A Laptop or PC to serve as a client

# An EC2 Linux Server as a web server (This is where you will install WordPress)

# An EC2 Linux server as a database (DB) server

`Use RedHat OS for this project`

# Step 1 — Prepare a Web and Database Server

![Web and Database Server](./images/Web-and-Database-Server.jpg)

# Created and Attached the EBS volumes to the Web and Database Servers

![Attached Volumes](./images/attached-volumes.jpg)

# Use `lsblk` command to inspect what block devices are attached to the server 

![Lsblk command](./images/webserver-lsblk.png)

# Use `sudo ls /dev` to see all the devices in the Linux System

![List all the devices](./images/webserver-device.jpg)

# Use `sudo lsblk` utility to view the newly configured partition on each of the 3 disks.

![Newly Configured Partition](./images/webserver-partition.jpg)

# Installation of LVM (Logical Volume Management Package)

![Installation of LVM](./images/lvm-installation.jpg)

# Checking All the disk partitions using `sudo lvmdiskscan`

![All the disk partitions](./images/lvmdiskscan-partitions.jpg)

# Use `sudo pvcreate` to create physical volumes

![Physical Volumes](./images/physical-volumes.jpg)

# Use `sudo vgcreate volume-group-name individual-physical-volumes` to create a volume group

![Volume Groups](./images/volume-groups.jpg)

# Use `sudo lvcreate -n name-of-logical-volume -L size-of-the-disk volume-group-name`

![Logical Volumes](./images/logical-volumes.jpg)

# Use `mkfs.ext4` to format the logical volumes with ext4 filesystem

![Format to Mk File System](./images/format-to-mkfs-filesystem.jpg)

# Mounting and Restoring files

![App files mounts and Log mounts](./images/mounting-the-disks-on-to-the-server.jpg)

![App files mounts and Log mounts](./images/mounting-the-disks-on-to-the-server2.jpg)