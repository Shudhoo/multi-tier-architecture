Multi-Tier Architecture with AWS CloudFormation
Overview
This CloudFormation template creates a multi-tier architecture for hosting a website with:
•	2 EC2 instances (Public & Private)
•	1 RDS instance (MySQL)
•	A VPC with subnets, security groups, and routing
Architecture
•	VPC: Created with public and private subnets
•	Internet Gateway (IGW) & Route Table: Enables public access for the Public EC2 instance
•	Public Subnet: Hosts a Public EC2 instance that allows SSH (22) and HTTP (80) access (not recommended for production)
•	Private Subnet: Hosts a Private EC2 instance (accessible only from the Public EC2 instance, acting as a jump server)
•	DB Subnet: Hosts the RDS instance, accessible only from the Private EC2 instance on port 3306
•	Security Groups:
o	Public EC2: Allows SSH and HTTP from anywhere (not recommended for production)
o	Private EC2: Allows SSH only from Public EC2
o	RDS: Allows connections only from Private EC2 on port 3306
Resources Created
•	VPC and Subnets (Public, Private, DB Subnet)
•	EC2 Instances (Public & Private)
•	RDS Instance (MySQL)
•	Security Groups (for EC2 and RDS)
•	Internet Gateway and Route Tables
•	Elastic IP (EIP) for Public EC2
•	Route 53 Hosted Zone and A Record (Optional, if using a domain)

