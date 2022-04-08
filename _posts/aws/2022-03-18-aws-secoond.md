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


![setup_first](/image/AWS_blog_2/Ec2.png) 


I create a server by clicking EC2 in the AWS service menu.



 ![setup_first](/image/AWS_blog_2/Ec2_2.png)  

I used Amazon Linux. Use the desired Amazon Machine Image and press select

![setup_first](/image/AWS_blog_2/Ec2_3.png)  
Then, set the instance type you want. I used the free version.


![setup_first](/image/AWS_blog_2/Ec2_4.png)  

Subnets are automatically added when you select the VPC you selected for the network.



![setup_first](/image/AWS_blog_2/Ec2_5.png)  
When creating the security group, I allowed only SSH and HTTP to the security group first. I will connect to the newly created server from the outside through SSH, and I will use apache as the web server, so I made a security group that allows HTTP(80). You can set this part according to your situation.


![setup_first](/image/AWS_blog_2/Ec2_6.png)  

Finally, you can download the key used to connect to the server in the review (STEP 7). You must have the corresponding key to access the server , so make sure to keep it after downloading . It is impossible to create a server without downloading, so you must download it and never delete it.



https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html

There are two ways to access the server. There is a way to access from a Linux server and a way to access from a Windows server with putty. Please refer to the user guide on the Amazon site for this access method


6. DNS matching Elastic Ips
After checking the connection through putty, assign a fixed authorized ips to the dns and match the server

Elastic IPs



![setup_first](/image/AWS_blog_2/ips_1.png)  

In the navigation with the Network & Security section, select elastic ip and click allocate Elastic ip address

![setup_first](/image/AWS_blog_2/ips_2.png)  

I set the network border group to US-East -1, so that's how I set it. Create an IP address after setting it to the network border group that you set

![setup_first](/image/AWS_blog_2/ips_3.png)  


![setup_first](/image/AWS_blog_2/ips_4.png)  

If IP is set, you can set the instance by clicking Associate Elastic ip address on the Action button. Set the appropriate instance

![setup_first](/image/AWS_blog_2/ips_5.png)  


Finally, you can see that the public ipv5 address has changed. Now a website server has been created. You can access it by entering the ipv4 address or ipv4 DNS address on the homepage.



![setup_first](/image/AWS_blog_2/last.png)  


As you can see, if you succeed in the server, you can access the ip address you created. But I don't know why, but I was able to access it about 30 minutes after all the completion. We will end the server setting and gate and subnet setting using aws.



  <video width="640" height="480" controls>
   <source src="/video/aws_1.mp4" type="video/mp4">
   </video>  

   <video width="640" height="480" controls>
   <source src="/video/aws_2.mp4" type="video/mp4">
   </video>  
   