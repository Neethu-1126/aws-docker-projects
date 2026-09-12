# Project 1 - AWS Website Hosting

## Project Overview

Hosted a static website on an AWS EC2 instance using Apache web server.

## AWS Services Used

- IAM
- EC2
- EBS
- AMI
- Security Groups
- S3
- AWS CLI
- CloudWatch

## Architecture

User
  |
  v
EC2 Instance
  |
  v
Apache Web Server
  |
  v
Website

## Implementation

1. Created an IAM role for the EC2 instance.
2. Launched an Ubuntu EC2 instance.
3. Used EBS as the instance's storage.
4. Installed and configured Apache.
5. Created website content under `/var/www/html/`.
6. Configured Security Group rules for web access.
7. Used AWS CLI for AWS-related operations.
8. Created an AMI from the configured EC2 instance.
9. Used S3 for object storage.
10. Used basic CloudWatch monitoring.

## Key Concepts Learned

- EC2 instance hosting
- EBS storage
- AMI creation
- Security Groups
- IAM roles
- Apache web server
- AWS CLI
- CloudWatch monitoring
- S3 storage
