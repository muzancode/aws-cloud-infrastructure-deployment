# Section 1 – VPC & Networking

## VPC
- **Name:** Muzan-VPC
- **CIDR:** `10.0.0.0/16`
- **Region:** us-east-1

## Subnets

| Name | Type | CIDR | Availability Zone |
|---|---|---|---|
| Public-Subnet-1 | Public | `10.0.0.0/24` | us-east-1a |
| Public-Subnet-2 | Public | `10.0.2.0/24` | us-east-1b |
| Private-Subnet-1 | Private | `10.0.1.0/24` | us-east-1a |
| Private-Subnet-2 | Private | `10.0.3.0/24` | us-east-1b |

## Internet Gateway
- **Name:** Muzan-IGW
- **State:** Attached to Muzan-VPC

## NAT Gateway
- **Name:** Muzan-NAT
- **Location:** Public-Subnet-1
- **Type:** Public

## Route Tables

### Public-RT
- `0.0.0.0/0` → Internet Gateway
- Associated with: Public-Subnet-1, Public-Subnet-2

### Private-RT
- `0.0.0.0/0` → NAT Gateway
- Associated with: Private-Subnet-1, Private-Subnet-2
