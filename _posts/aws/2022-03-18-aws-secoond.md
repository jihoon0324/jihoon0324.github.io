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



2. Subnetting



3. Create an Internet gateway


4. Making a writing table