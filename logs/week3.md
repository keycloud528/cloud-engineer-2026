# Week 3 - Database Lab

## Day 9 - RDS Architecture Lab

Today I built a complete AWS database architecture by integrating EC2 instances with Amazon RDS and verified secure database connectivity within a private network.

### VPC Configuration

VPC
CIDR: 10.0.0.0/16

Subnets

Public Subnet
10.0.1.0/24 (AZ-a)

Private Subnet
10.0.2.0/24 (AZ-a)

Additional Subnet (for RDS requirement)
10.0.3.0/24 (AZ-c)

### Networking Components

Internet Gateway
Attached to the VPC

Route Tables

Public Route Table
0.0.0.0/0 → Internet Gateway

Private Route Table
10.0.0.0/16 → local only

### EC2 Instances

Bastion Host

Location: Public Subnet
Public IP: Enabled
SSH Access: My IP only

Private EC2

Location: Private Subnet
Public IP: Disabled
SSH Access: Allowed only from Bastion host

### RDS Configuration

Database Engine
MySQL

Instance Type
db.t3.micro

Storage
20 GiB

Deployment
Single-AZ

Public Access
Disabled

VPC
Same as EC2 instances

DB Subnet Group
Includes subnets from multiple Availability Zones

### Security Configuration

RDS Security Group

Inbound Rule

MySQL (3306)
Source: Private EC2 Security Group

This allows only the application server (Private EC2) to access the database.

### Connection Flow

WSL → Bastion → Private EC2 → RDS

Steps

1. Connected from WSL to Bastion EC2 using SSH
2. Accessed Private EC2 through Bastion host
3. Installed MySQL client on Bastion
4. Connected to RDS using endpoint and credentials

### Verification

RDS connection test

Successfully connected to RDS from EC2 environment

Executed SQL commands

---
</> SQL

CREATE DATABASE testdb;

USE testdb;

CREATE TABLE users (
  id INT,
  name VARCHAR(50)
);

INSERT INTO users VALUES (1, 'Key');

SELECT * FROM users;
---
Result

Data was successfully inserted and retrieved from the database

### Issues Encountered
1. VPC mismatch error

RDS and EC2 were initially in different VPCs

>Solution
Aligned RDS VPC with EC2 VPC

2. Subnet / AZ requirement

RDS required subnets in multiple Availability Zones

>Solution
Created an additional subnet in a different AZ

3. Private EC2 internet access

Private EC2 could not install packages

>Solution
Used Bastion host for package installation

### Key Concepts Learned

RDS
DB Subnet Group
Multi-AZ requirement
Security Group-based access control
Private subnet architecture
EC2 to RDS connection

### Key Insight

Databases should be placed in private subnets and accessed only through application servers.

This structure represents a standard backend architecture in cloud environments.

-----


