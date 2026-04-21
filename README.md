\# AWS Secure VPC with NAT Gateway



\## Overview

Designed and implemented a secure VPC architecture on AWS with public and private subnets.  

Private instances access the internet through a NAT Gateway without exposing them publicly.



\---



\## Architecture

\- VPC CIDR: 10.0.0.0/16

\- Public Subnet (for NAT + Internet Gateway)

\- Private Subnets (for internal resources)

\- Internet Gateway attached to VPC

\- NAT Gateway with Elastic IP

\- Route Tables configured for public and private traffic



\---



\## Key Features

\- Private instances have \*\*no public IP\*\*

\- Outbound internet access via NAT Gateway

\- Multi-AZ design

\- Secure network segmentation



\---



\## Routing

\- Public Route Table:

&#x20; - 0.0.0.0/0 → Internet Gateway



\- Private Route Tables:

&#x20; - 0.0.0.0/0 → NAT Gateway

&#x20; - 10.0.0.0/16 → local



\---



\## Testing

\- Launched EC2 instance in private subnet

\- Verified internet connectivity:

```bash

ping google.com

