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
