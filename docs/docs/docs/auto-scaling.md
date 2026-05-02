# Section 5 – Auto Scaling

## Launch Template
- **Name:** WebTier-LT
- **Instance Type:** t2.micro
- **Security Group:** WebTier-SG

## Auto Scaling Group
- **Name:** Muzan-ASG
- **Desired Capacity:** 2
- **Minimum:** 2
- **Maximum:** 6
- **Subnets:** Private-Subnet-1, Private-Subnet-2
- **AZ Distribution:** Balanced best effort

## Scaling Policy
- **Type:** Target Tracking
- **Metric:** Average CPU Utilization
- **Target:** 60%
- **Warmup:** 300 seconds

## CloudWatch Alarms
| Alarm | Condition | Action |
|---|---|---|
| Scale Out | CPU ≥ 60 for 3 datapoints (3 min) | Add instances |
| Scale In | CPU < 42 for 15 datapoints (15 min) | Remove instances |
