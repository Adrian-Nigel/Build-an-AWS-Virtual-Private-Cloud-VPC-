# Build a Virtual Private Cloud

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-vpc)

**Author:** Adrian Nigel  
**Email:** adriannigel32@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://nextwork.ai/fulfilled_white_majestic_sea_otter/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how to:
-☁️ Create an Amazon VPC.
-🥅 Create a public subnet.
-🚪 Create an internet gateway.



### What is Amazon VPC?

### Personal reflection

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will:
-Access the VPC console in AWS.
-Create a VPC.


### How VPCs work

VPCs (Virtual Private Clouds) are isolated private networks inside the cloud. The purpose of a VPC is to allow me to keep my resources private and secure inside the AWS cloud.

### Why there is a default VPC in AWS accounts

There has been a default VPC in my account since it was created. AWS already set up this default VPC so that I can deploy resources such as RDS and EC2 instances on the go without having to set up my own VPC from scratch.

![Image](http://nextwork.ai/fulfilled_white_majestic_sea_otter/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is the range of IP addresses that my VPC will allocate to the resources needed for my AWS account.

---

## Subnets

### What I did in this step

In this step, I will launch a subnet inside the VPC.

### Creating and configuring subnets

Subnets are a range of IP addresses inside a VPC(Virtual Private Cloud). They can be explained as subsections of my VPC.
There are already subnets in my account, one for every availability zone in the region where I have set up my VPC. 
My region (North Virginia) had six default subnets.

### Public vs private subnets

There are differences between public and private subnets, which are:
-Public subnets send and receive traffic from the internet. Private subnets block incoming internet traffic.

-Public subnets link to an internet gateway. Private subnets lack this direct route.

-Public resources get public and private IP addresses. Private resources use private IP addresses only.

For a subnet to be considered public, it has to be connected to an Internet gateway.

![Image](http://nextwork.ai/fulfilled_white_majestic_sea_otter/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled the auto-assign public IPv4 address. to directly receive an internet-routable IP address at launch. This setting makes sure that any EC2 instance launched in that subnet will directly receive an internet-routable IP address at launch, so that I won't have to create one manually - a huge time saver😃!

---

## Internet gateways

### What I did in this step

In this step, I will connect the VPC to the internet using an internet gateway.

### Setting up internet gateways

(Internet gateways) are components managed by the VPC that allow the Virtual Private Cloud (VPC) to connect to the public internet.

Attaching an internet gateway to a VPC means. that resources in my VPC can now access the internet.
If I missed this step, resources within my EC2 instance with a public address would not be made available to other users. Thus making applications hosted on the server unavailable too. 

![Image](http://nextwork.ai/fulfilled_white_majestic_sea_otter/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will:
-Open a handy tool (called AWS CloudShell) to run commands.

-Run AWS CLI commands to set up a VPC, subnet, and internet gateway.


### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is a free, browser-based shell launched directly from the AWS Management Console. 

It comes pre-authenticated with your console credentials and pre-installed with popular developer utilities like the AWS CLI, Python, and Git, enabling you to manage cloud resources without a local setup.

CLI(Command Line Interface) is a tool that allows you to interact with and manage resources on your computer using text commands directly instead of clicking visual icons and menus. 
In this case, to interact with and manage Amazon Web Services (AWS).

### Debugging my setup

To set up a VPC, you can run the command"aws ec2 create-vpc --cidr-block 10.0.0.0/24 --query Vpc.VpcId --output text", and to set up a subnet, you can use the command  "aws ec2 create-subnet --vpc-id vpc-0de4e71de6f3f1fa2 --cidr-block 10.0.0.0/27".
 Make sure to avoid errors by including our CIDR block range. The parameter is "--cidr-block", which defines a subnet's CIDR block range. Without this, the CLI cannot create the subnet because it doesn’t know which IP addresses to allocate for it.

![Image](http://nextwork.ai/fulfilled_white_majestic_sea_otter/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

The AWS Management Console is fantastic for learning and having a visual guide; however, the CLI provides the speed and versatility that professionals need for complex tasks.

I included this part to show how AWS CLI often becomes your go-to tool. Engineers use the CLI to automate tasks using scripts, making the CLI essential for managing your cloud environment in an efficient way.

---

---
