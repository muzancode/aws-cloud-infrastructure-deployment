# AWS Cloud Infrastructure Deployment

**Author:** Muzan Abbas

A production-grade AWS infrastructure deployment featuring a secure, scalable, and highly available multi-tier architecture.

## Architecture Overview

- **VPC** with CIDR `10.0.0.0/16` across 2 Availability Zones
- **4 Subnets**: 2 public (`10.0.0.0/24`, `10.0.2.0/24`) and 2 private (`10.0.1.0/24`, `10.0.3.0/24`)
- **Internet Gateway** for public subnet access
- **NAT Gateway** for private subnet outbound access
- **Application Load Balancer** (internet-facing, port 80)
- **EC2 instances** (t2.micro) in private subnets via Auto Scaling
- **RDS MySQL** (Multi-AZ, private subnets)
- **CloudWatch** alarms for CPU-based auto scaling

## Sections

| Section | Description |
|---|---|
| [Networking](docs/networking.md) | VPC, Subnets, IGW, NAT, Route Tables |
| [Security Groups](docs/security-groups.md) | ALB-SG, WebTier-SG, Database-SG |
| [Database](docs/database.md) | RDS MySQL, Multi-AZ, Subnet Group |
| [Load Balancer & Web Tier](docs/load-balancer.md) | ALB, Listener, Target Group, EC2 |
| [Auto Scaling](docs/auto-scaling.md) | Launch Template, ASG, Scaling Policy, CloudWatch |

## Architecture Diagram

```
Internet
    │
[Internet Gateway]
    │
[ALB - Public Subnets]
    │
[EC2 Web Tier - Private Subnets]  ←→  [Auto Scaling Group]
    │
[RDS MySQL - Private Subnets, Multi-AZ]
```
