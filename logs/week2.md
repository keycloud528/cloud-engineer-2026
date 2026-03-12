# Week 2 - Networking Lab

## Day 7 - VPC Architecture Lab

Today I built a basic AWS VPC architecture with public and private subnets and verified connectivity using a Bastion host.

---

## VPC Configuration

VPC
CIDR: 10.0.0.0/16

Subnets

Public Subnet 
10.0.1.0/24

Private Subnet 
10.0.2.0/24

---

## Networking Components

Internet Gateway 
Attached to the VPC.

Route Tables

Public Route Table
0.0.0.0/0 → Internet Gateway

Private Route Table
10.0.0.0/16 → local only

---

## EC2 Instances

Bastion Host

Location: Public Subnet
Public IP: Enabled
SSH Access: My IP only

Private EC2

Location: Private Subnet 
Public IP: Disabled 
SSH Access: Allowed only from public subnet (10.0.1.0/24)

---

## SSH Connection Flow

WSL → Bastion Host → Private EC2

Steps

1. Connected from WSL to Bastion EC2 using SSH
2. Copied the key pair to Bastion
3. Used Bastion to SSH into the Private EC2 instance

---

## Verification

Private EC2 network test

ping google.com

Result

100% packet loss

This confirms that the private EC2 instance cannot access the internet directly because there is no NAT Gateway.

---

## Key Concepts Learned

VPC
Subnet
CIDR
Internet Gateway
Route Table
Public vs Private subnet
Bastion Host

---

## Day 8 — S3 Storage and CLI Lab

### Environment
Local machine: WSL Ubuntu
Cloud: AWS S3

---

### S3 Setup

Created S3 bucket:

ce-bootcamp2026-s3

Uploaded objects:

test.txt
day8.txt 
s3-lab.txt 

---

### AWS CLI Setup

Installed AWS CLI v2 using the official AWS installer.

Commands used:

curl https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip 
unzip awscliv2.zip 
sudo ./aws/install

Configured authentication:

aws configure

---

### S3 CLI Operations

List buckets

aws s3 ls

List objects

aws s3 ls s3://ce-bootcamp2026-s3/

Upload object

aws s3 cp s3-lab.txt s3://ce-bootcamp2026-s3/

Download object

aws s3 cp s3://ce-bootcamp2026-s3/day8.txt .

---

### Key Learning Points

- S3 uses object storage instead of traditional file systems
- S3 objects are identified using keys, not folders
- AWS CLI allows direct control of cloud resources
- IAM permissions are required for S3 access
