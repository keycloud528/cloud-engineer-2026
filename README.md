# Cloud Engineer 2026 Immersion Plan

## Goal
Become job-ready Cloud Engineer in 6 months.

## Period
2026.03.02 - 2026.08.31

## Projects
- [ ] EC2 WordPress Deployment
- [ ] Custom VPC Architecture
- [ ] Dockerized WordPress
- [ ] Load Balancer + Auto Scaling
- [ ] CI/CD Pipeline
- [ ] Final Architecture Presentation (English)

## Study Log
Weekly execution logs will be documented per project.

Week 1: EC2 basics, SSH connection, S3 Fundamentals

Day 1: Git environment setup completed.

---

Day 2: Cloud Basics

# Topics Learned
- Learned cloud computing fundamentals
- Understood Region vs Availability Zone
- EC2 is deployed in a specific Availability Zone
- High availability must be designed by the user

---

Day 3: EC2 Launch and SSH Connection

# Topics Learned
- AWS Cloud Practitioner Essentials (Module 1)
- EC2 fundamentals
- SSH remote connection
- Key pair authentication
- Security Groups
- EC2 Stop vs Terminate

# Hands-on Practice
Today I launched my first EC2 instance using Amazon Linux.

I created an SSH key pair and downloaded the private key file (.pem).
Using WSL Ubuntu on my local machine, I connected to the EC2 instance via SSH.

After successfully connecting to the server, I executed several basic Linux commands such as:

- whoami
- uname -a
- ls

Finally, I stopped the EC2 instance to avoid unnecessary charges.

# Key Takeaways
This was my first experience launching and accessing a cloud server.

I now understand how a local machine connects to a remote EC2 server using SSH and key pair authentication.

I also learned the difference between stopping and terminating an EC2 instance.

---

Day 4: AWS Architecture Basics

# Topics Learned
- AWS Cloud Practitioner Essentials (Module 2)
- High availability concepts
- Horizontal scaling vs Vertical scaling
- Load Balancer fundamentals
- Auto Scaling basics
- CLI vs SDK
- AMI (Amazon Machine Image)
- Public IP vs Private IP networking concept

---

Day 5: Serverless and Containers

# Topics Learned
- AWS Lambda fundamentals
- Event-driven serverless architecture
- Container and container image concepts
- Load Balancer and Auto Scaling architecture review
- Introduction to Amazon S3 storage

---

Day 6: AWS Global Infrastructure

# Topics Learned
- AWS Global Infrastructure
- Edge Locations
- Infrastructure as Code (IaC)
- AWS CloudFormation
- Choosing an AWS Region

---

Week 2

Day 7: VPC Networking and Bastion Architecture

# Topics Learned
- AWS VPC (Virtual Private Cloud) architecture fundamentals
- CIDR block configuration (10.0.0.0/16)
- Public subnet vs Private subnet design
- Internet Gateway setup and routing to the internet
- Route Table configuration for public and private networks
- Security Group configuration for controlled SSH access
- Bastion Host architecture for secure access to private instances
- SSH connection flow: WSL → Bastion Host → Private EC2
- Private network isolation verification (no internet access without NAT Gateway)

# Hands-on Practice
Built a basic VPC networking architecture in AWS.

Created a VPC, public and private subnets, Internet Gateway, and route tables.
Deployed a Bastion EC2 in the public subnet and a Private EC2 in the private subnet.

Connected from WSL → Bastion → Private EC2 using SSH.

Verified that the private EC2 cannot access the internet without a NAT Gateway.

# Key Takeaways
I learned how to design a basic VPC network with public and private subnets.

I also understood how Bastion hosts allow secure SSH access to private servers and how route tables control internet connectivity.

---
Day 8: AWS Storage and S3

# Topics Learned
- AWS Storage types: Block, Object, File storage
- Amazon S3 object storage architecture
- S3 bucket and object structure
- Flat address space concept
- EBS snapshots and incremental backup
- AWS CLI installation and configuration
- IAM permissions for S3 access

---

# Hands-on Practice
Today I installed AWS CLI on my WSL environment and configured authentication using IAM access keys.

I created an S3 bucket and uploaded objects using both the AWS Console and the AWS CLI. I also practiced downloading and listing objects directly from the terminal.

Additionally, I tested pseudo-folder structures in S3 by uploading an object using a key path.

# Key Takeaways
I learned that S3 is not a traditional filesystem but an object storage system that uses keys instead of directories.

Using AWS CLI to interact with S3 gave me a better understanding of how cloud storage can be managed programmatically.
