# Section 2 – Security Groups

## ALB-SG (Load Balancer)
| Direction | Protocol | Port | Source |
|---|---|---|---|
| Inbound | HTTP | 80 | `0.0.0.0/0` |
| Inbound | HTTPS | 443 | `0.0.0.0/0` |
| Outbound | All | All | `0.0.0.0/0` |

## WebTier-SG
| Direction | Protocol | Port | Source |
|---|---|---|---|
| Inbound | HTTP | 80 | ALB-SG |
| Outbound | All | All | `0.0.0.0/0` |

## Database-SG
| Direction | Protocol | Port | Source |
|---|---|---|---|
| Inbound | MySQL/Aurora | 3306 | WebTier-SG |
| Outbound | All | All | `0.0.0.0/0` |
