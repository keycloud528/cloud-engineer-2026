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
