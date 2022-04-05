---
title: "SAIT Assingment -Blog2"
excerpt: "school assginment for blog 2 "

categories:
  - AWS
tags:
  - AWS
last_modified_at: 2022-03-18
---

# Website construction phase

The purpose of this blog is to put the actual website on the server and run it. Let's use the functionality in AWS to drive the actual website.



1. Create vpc
     What is VPC?
  It is not a real private network, but a virtual private network.
It is vpn that makes it work as if it is actually on the same network but on another network.

2. Subnetting
     What is Subnetting?
Subnetting is the process of creating a subnetwork (also known as a subnet) within a network. Network interfaces and devices within a subnet can communicate with each other directly. Routers facilitate communication between different subnets.

3. Create an Internet gateway
  what is gateway

  An Internet Gateway is a redundant, horizontally scaled, and is a highly available VPC component. It allows communication between instances in your VPC and the internet using VPC route tables for internet-routable traffic.





---------------------------------------------------------------------------------------
Sequence

First of all . log in with your account in AWS




1. Create a VPC after logging in
  ![setup_first](/image/AWS_blog_2/vpc_1.png)  

Create a vpc by clicking vpc in the service menu
    ![setup_first](/image/AWS_blog_2/vpc_2.png)  
 Set the vpc name in the Name tag section. I did it with sait_blog. Any name is possible. In case of using various vpc, it is also possible with a domain name ex) sait_blog.com.  
   ![setup_first](/image/AWS_blog_2/vpc_3.png)  
Right-click on vpc and click Edit DNS hostnames.
Then a new window will open, set DNS hostname to ENable.
This is to automatically name the server created on the network I created.

2. Subnetting

![setup_first](/image/AWS_blog_2/subnet1.png)  

Click Subnets in the line below your VPCS and then click "CREATE subnet", the screen above appears. If you open the vpc ID select bar here, you can check the name of the VPC you created. Click the name of the vpc to open the subnet setting section. A total of 4 subnets were created, 2 web subnets and 2 db subnets were created. For security reasons, I created two different subnets each.
![setup_first](/image/AWS_blog_2/subnet2.png)  
When you create a subnet, the following table is displayed. Let's check if the subnet address is the same as the subnet address you created.


3. Create an Internet gateway
I  create an internet gateway and match it with the IPv4 address (10.200.0.0/16) created in VPC .

![setup_first](/image/AWS_blog_2/gateway1.png) 

click  the create internet gateway and add name 
in my case I wrote name as sait_blog  and click the create internet gateway button.

![setup_first](/image/AWS_blog_2/gateway2.png)  
now click the actions and select attac to VPC

![setup_first](/image/AWS_blog_2/gateway3.png)  

this is for matching gateway to VPC
select vpc 

4. Create Route table

![setup_first](/image/AWS_blog_2/route1.png)  

A table is created in the vpc I created


![setup_first](/image/AWS_blog_2/route2.png) 

If you click the vpc router table you just created, you can see the router information at the bottom.


![setup_first](/image/AWS_blog_2/route3.png)  

![setup_first](/image/AWS_blog_2/route5.png)  

Check that status is active


5. Create EC2 server 

I create a server by clicking EC2 in the AWS service menu.