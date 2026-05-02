# Section 4 – Load Balancer & Web Tier

## Application Load Balancer
- **Name:** Muzan-ALB
- **Type:** Application
- **Scheme:** Internet-facing
- **Subnets:** Public-Subnet-1, Public-Subnet-2

## Listener
- **Protocol:** HTTP
- **Port:** 80
- **Action:** Forward to WebTier-TG

## Target Group (WebTier-TG)
- **Target Type:** Instance
- **Protocol:** HTTP
- **Port:** 80
- **Healthy Targets:** 2

## EC2 Instances
| Instance | Subnet | Private IP | Health |
|---|---|---|---|
| Instance 1 | Private-Subnet-2 (us-east-1b) | 10.0.3.171 | Healthy |
| Instance 2 | Private-Subnet-1 (us-east-1a) | 10.0.1.237 | Healthy |
