# Week 1 — Foundations (WSL + Git + AWS Basics)

## Goals for this week
- Build a stable local environment (Windows 11 + WSL2 Ubuntu)
- Set up Git + GitHub SSH workflow
- Understand core AWS fundamentals (Region/AZ, EC2, IAM basics)
- Launch an EC2 instance and connect via SSH
- Start writing clean engineering logs (reproducible steps)

---

## Day 1 — Local Environment Setup (WSL2 + GitHub Repo)

### What I did (step-by-step)
1) Created a GitHub repository: `cloud-engineer-2026`
2) Set up basic repository structure and updated `README.md`
3) Installed WSL2 on Windows 11 and launched Ubuntu
4) Updated Linux packages and installed Git

### Commands I used
wsl --install
uname -a
sudo apt update
sudo apt upgrade -y
sudo apt install git -y
git --version

### Key Concepts (my own words)
WSL2: A Linux environment running inside Windows for development.
Git: A tool to track file changes over time.
GitHub: A remote place to store Git repositories.

---

## Day 2 — GitHub SSH Authentication + Repo Workflow

### What I did (step-by-step)
1) Generated an SSH key in Ubuntu (WSL)
2) Added the public key to GitHub
3) Tested SSH connection to GitHub
4) Cloned the repository into WSL
5) Practiced basic Git workflow: add → commit → push
6) Fixed Git identity error by setting user.name and user.email

### Commands I used
ssh-keygen -t ed25519 -C "my_email@example.com"
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com

git clone git@github.com:keycloud528/cloud-engineer-2026.git
cd cloud-engineer-2026

git status
git add <file>
git commit -m "message"
git push

git config --global user.name "Your Name"
git config --global user.email "you@example.com"

### Key Concepts
- SSH: A secure way to connect/authenticate without using passwords.
- Key pair(public/private): GitHub stores my public key; I keep the private key.
- Staging area(git add): A "review zone" before saving changes into history

---

## Day 3 - AWS Cloud Basics + EC2 Launch + SSH Connection

### Learning(AWS Skillbuilder)
- Completed: AWS Cloud Practitioner Essentials - Module 1
- Key topics:
 - Regions vs. Availability Zones
 - Shared Responsibility Model
 - Basic AWS service categories(compute, storage, networking)

### Hands-on(EC2)

### What I did(step-by-step)
1) Opend AWS console and selected a Region(Seoul)
2) Launched and EC2 instance(Amazon Linux/t2.micro)
3) Created an EC2 key pair(RSA) and downloaded the .pem file
4) Configured Security Group to allow SSH(Port 22) from My IP
5) Copied the .pem key into WSL and set correct permissions
6) Connected to the EC2 instance using SSH
7) Ran basic Linux commands on the remote server
8) Stopped the EC2 instance to reduce costs

### Commands I used(WSL)

mkdir -p ~/keys
cp /mnt/c/Users/<WindowUsers>/Desktop/Cloud/<key>.pem ~/keys/
chmod 400 ~/keys/<keys>.pem

ssh -i ~/keys/<key>.pem ec2-user@<public-ip>

whoami
uname -a
ls

### Key Concepts
- EC2: A virtual server running in an AWS data center.
- SSH: The method used to securely access the server via terminal.
- Key pair: A digital lock-and-key system for SSH login to EC2.
- Security Group: A virtual firewall controlling network traffic.
- Stop vs. Terminate:
 - Stop: Shut down compute, keep storage/data
 - Terminate: delete the instance(usually deletes storage too)

### What I can explain now
- "I launched an EC2 instance and connected vis SSH using a key pair."
- "A Security Group controls which ports are open to the internet."
- "Stopping an instance preserves data; terminating removes the instance."

### Output / Evidence
- SSH login succeeded from WSL Ubuntu.
- Instance state changed to stopped after the test.

---

## Day 4 – AWS Architecture Basics

### Topics
- AWS Cloud Practitioner Essentials (Module 2)
- High Availability
- Auto Scaling
- Load Balancing
- Horizontal vs Vertical Scaling
- CLI vs SDK
- AMI basics
- Public IP vs Private IP

### Hands-on
- Started EC2 instance
- Connected via SSH using WSL
- Verified server access
- Stopped EC2 instance

### Key Learnings
High availability in AWS is achieved using multiple EC2 instances, load balancers, and auto scaling.

Horizontal scaling (adding more instances) is generally preferred over vertical scaling because it improves fault tolerance.

EC2 instances communicate internally using private IP addresses, while public IP addresses allow internet access.

