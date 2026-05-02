# Section 3 – RDS Database

## Configuration
- **Engine:** MySQL Community
- **Status:** Available
- **Multi-AZ:** Enabled
- **Instance Size:** db.t3.medium
- **Publicly Accessible:** No
- **Security Group:** Database-SG (port 3306 from WebTier-SG only)

## Subnet Group
- **Name:** private-db
- **Subnets:** Private-Subnet-1 (us-east-1a), Private-Subnet-2 (us-east-1b)
