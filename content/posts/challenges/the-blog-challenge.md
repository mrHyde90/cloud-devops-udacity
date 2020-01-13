---
title: "The Blog Challenge"
date: 2020-01-12T16:17:14-06:00
draft: false
description: "A little introduction to Infrastructure Diagrams"
author: "Jose Alfredo"
tags: ["challenges"]
---

### Index
1. Availability Zones
2. VPC (Virtual Private Cloud)
3. Public vs Private subnet
4. IGW Internet Gateway
5. Network Address Translation NAT'S
6. AutoScaling
7. Load Balancers
8. Security Groups
9. Routing Table
10. S3

# Infrastructure Diagrams

Have you ever wondered what's behind those apps you use? or how they work? those apps worth millions of dollars
and that are on every mobile phone, applications like facebook, netflix, instagram, twitter.
Today, in order to understand a little about how they work, we're going to structure a basic application. Then I'll explain step by step what each thing is for. 

For a better explain, Imagine that you have an empty field, this empty field is like you aws (GCP, IBM cloud) account. 


![Example image](/images/empty.GIF)



## Availability zones
So the first thing that we want to do is create a house in this empty field, the house is like you availability zone.These are data centers, the physical part where your server will be hosted.

![Example image](/images/house1.GIF)

A litle problem can be, Imagine your house burning down or falling down. You need to build other house to avoid to sleep outside. This house will be a copy of your first house. 

So the reccomendations for availability zone is include more than one to avoid failures.

![Example image](/images/house2.GIF)



## VPC (Virtual Private Cloud)
Now one problem can be the security of your houses, you need more privacy, imagine an unknown person enter in your field! So the answer is:

![Example image](/images/VPC1.GIF)

This is a VPC, its your own network, this network is isolated from the world, from everything. like the grids can block the unknown people, the vpc can block the unknow IP addresses.

## Public vs Private subnet
But you have a great idea, you want to create 2 rooms, one room is yours and the second room you want to rent it. So this is the concept of private and public subnet. in the private subnet you wanna do databases deploys or have sensitive data. While in the public you will receive the inboud internet traffic of whatever resource. In the house example, in your room you will have your clothes and sensitive data while in the other room is for anyone who wants to rent it.

![Example image](/images/privatepublic.GIF)

## IGW Internet Gateway 
One problem can be, How do you rent the room if your field is close to people?


![Example image](/images/IGW.GIF)


One thing that you can do is just open your field for anyone how wants to rent the room. 


So this is the concept of IGW, VPC is isolated, IGW  have the goal of enable inbound and outbound traffic from the internet to your VPC. But dont worry, this keeps the private service protected from inbound connections. 

SO, you'll open the gates for people who want to see the room

![Example image](/images/IGW2.GIF)

## Network Address Translation NAT'S
But your room is really private! nothing and no one can enter, but you need your room have access to the world if you wanna store your clothes or pictures.So will open your room.


NAT's is used to Provides outbound internet access to resources in private subnets. Its says "Translate" incoming public traffic into private traffic. Normally the NATs is placed in the public subnet because it needs
public access itself.


Maybe in the house example it's like having the door in the next room

![Example image](/images/Nat1.GIF)

## AutoScaling

Now we need to put the beds, the number of beds is the number of people in the room. But imagine we have a couple who want to rent the room. 

![Example image](/images/Auto1.GIF)


So we need to put other bed, but if the people want to share the room with other friend? we need other bed and sometimes we want to delegate this kind of jobs to other person. So if the people need other bed, they
can talk with this person and put other bed. 


![Example image](/images/Auto2.GIF)


So if the first house burns down or falls down, this person can help us to move our clothes and beds to the other house.


So the beds are the concepts for instances or servers, while the person in charge of bringing more beds or moving things is the Autoscaling. 


The autoscaling has 2 functionalities: High availability and elasticity.


High availabilty means, if your private subnet down the autoscaling will make a copy of this to keep on the network 2.


Elasticity means: If we need more servers, the autoscaling will add more servers and on the other hand will remove servers.

## Load Balancers
The load balancers is the service to distribute work request meant for a target (target group is a collection of servers providing a common service).

imagine that you have 2 servers and the first is handling 60 request and the other none. The load balancers will distribute the work in the 2 servers.


So in our house example, imagine that the couple wanna sleep together in one bed, but the bed can't handle both. The load balancer (in this case other person) will distribute 
the couple in 2 beds.

![Example image](/images/load1.GIF)

## Security Groups

A security group is a collection of networking rules for inbound and outbound traffic. A security group can be scoped to a single IP address.


So in our house example, maybe can be a certain rules about what kind of people can be use the bed. 


![Example image](/images/sg1.GIF)

## Routing Table
Routing tables is a set of entries or rules associated with one or more of your subnets inside your vpc. These rules allow or deny traffic to/from the addres ranges that you specify.


In our house example are rules that decide what kind of people can enter to the rooms.


![Example image](/images/routing1.GIF)

## S3
Finally, imagine that people want to keep their clothes or things inside the room. You need to buy a wardrobe.
![Example image](/images/S3.GIF)


so this is the final concept, S3 is a public service for users to upload or download files.


## The Cloud
Now that we have our house example finish, we wanna see the difference with our infrastructure in the cloud.

![Example image](/images/diagrama2.PNG)

1. First, you can see the S3 outside the vpc. Because S3 is a public service.
2. The security group at the level of the server.
3. The load balancer at the level of availability zones
4. Other differences that we can see are the auto scaling located inside the private network.


So these are the main concepts to create the infrastructure that you need to serve an application at the global level. These are the concepts that I have learned in the phase 1. These concepts are really useful to create One million dollar application, because you need all these concepts for 3 big ideas: Realiable, Scalable and maintainable. So I really enjoy this lection because I can see the overview of a good infrastructure or in this case a basic but good. So I wanna implement these concepts creating an application with a decent level.