## AWS CLOUD SOLUTION FOR 2 COMPANY WEBSITES USING A REVERSE PROXY TECHNOLOGY

`1 - SET UP A VIRTUAL PRIVATE NETWORK (VPC)`

![Modern-VPC](./Images/Modern-VPC1.png)

`2 - Enable DNS Hostnames for the VPC`

![Enable DNS Hostnames](./Images/Modern-VPC2.png)

![Enable DNS Hostnames2](./Images/Modern-VPC3.png)

`3 - Create an Internet Gateway`

![Internet-Gateway](./Images/Modern-IGW.png)
![Internet-Gateway2](./Images/Modern-IGW2.png)

`4 - Create subnets as shown in the architecture`

![Modern-PublicSubnets](./Images/Modern-PublicSubnet.png)

![Modern-PrivateSubnets](./Images/Modern-PrivtaeSubnets.png)

`5 - Create route table for the public subnet to use (Public Route Table)`

![Modern-PublicRTB](./Images/Modern-PublicRTB1.png)
![Modern-PublicRTB](./Images/Modern-PublicRTB2.png)

`6 - Create a route in the public route table and point to the Internet gateway`

![Modern-PublicRTB-IGW](./Images/Modern-PublicRTB-IGW.png)
![Modern-PublicRTB-IGW2](./Images/Modern-PublicRTB-IGW2.png)

`7 - Associate the public subnets to the created route table`

![Modern-PublicRTB-Subnet-Associations](./Images/Modern-PublicRTB-Subnet-Associations.png)

`8 - Create a NAT Gateway so that servers in the private subnet can reach the internet for example download stuff (Outbound)`

![Modern-NATGW](./Images/Modern-NATGW.png)
`9 - Create route table for the private subnet to use (Private Route Table)`

![Modern-PrivateRTB1](./Images/Modern-PrivateRTB1.png)
![Modern-PrivateRTB2](./Images/Modern-PrivateRTB2.png)
