# Project 2 - Highly Available AWS Web Application

## Project Overview

Built a highly available web application architecture on AWS using multiple Availability Zones.

The application uses an Application Load Balancer to distribute HTTP traffic across multiple EC2 instances.

## Architecture

User
  |
  v
Application Load Balancer
  |
  v
Target Group
  |
  +-------------------+
  |                   |
  v                   v
EC2 Instance A    EC2 Instance B
  |                   |
  +---------+---------+
            |
         Apache
         Web Server

## Network Architecture

VPC CIDR:

10.0.0.0/16

The VPC was divided into:

- Public Subnet A
- Public Subnet B
- Private Subnet A
- Private Subnet B

## AWS Services Used

- VPC
- CIDR
- Public Subnets
- Private Subnets
- Route Tables
- Internet Gateway
- NAT Gateway
- Network ACL
- Security Groups
- EC2
- Application Load Balancer
- Target Group
- Apache Web Server

## Application Load Balancer

The Application Load Balancer receives HTTP traffic on port 80 and forwards requests to the Target Group.

The Target Group uses HTTP on port 80 to communicate with the EC2 web servers.

## Security Groups

Security Groups were configured to control traffic between:

- Internet and ALB
- ALB and EC2 instances
- SSH access where required

The main web traffic flow uses:

HTTP
Port 80

## Target Group

The EC2 instances were registered as targets in the Target Group.

The ALB performs health checks to determine whether each EC2 instance is healthy.

After troubleshooting the configuration, both EC2 instances reached a healthy state.

## High Availability

Two EC2 instances were deployed across separate Availability Zones.

Traffic is distributed by the Application Load Balancer.

If one healthy target becomes unavailable, the ALB can route traffic to another healthy target.

## Networking

The Internet Gateway provides internet connectivity for resources in public subnets.

The NAT Gateway allows resources in private subnets to initiate outbound internet connections without making those resources directly accessible from the internet.

Route tables determine how traffic is routed between the subnets and gateways.

## Troubleshooting

During the project, several issues were investigated, including:

- Target Group initially showing unhealthy targets
- Connectivity problems
- Security Group configuration
- ALB to Target Group communication
- Port 80 configuration
- Health check configuration
- Internet connectivity

The final result was two healthy targets behind the Application Load Balancer and a working Apache web page.

## Key Concepts Learned

- VPC networking
- CIDR
- Public and private subnets
- Route tables
- Internet Gateway
- NAT Gateway
- Security Groups
- Network ACL
- Application Load Balancer
- Target Groups
- Health checks
- Multi-AZ high availability
- EC2 web servers
- Apache
