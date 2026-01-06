| Rule | Type | Protocol | Port | Source | Purpose |
|------|------|----------|------|--------|---------|
| 1    | SSH  | TCP      | 22    | IP     | Admin access |
| 2    | HTTP    | TCP      | 80   | 0.0.0.0/0      | Web traffic |
| 3    | HTTPS    | TCP      | 443  | 0.0.0.0/0      | Secure web |
| 4    | Custom TCP | TCP | 8080  | 10.0.0.0/8 | Internal API |

| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| Can't SSH to instance | Missing SSH Port 22 | Add Port 22 to SSH with your IP |
| Website not loading | HTTP/HTTPS not in security group | Inbound rules to allow HTTP from 0.0.0.0/0 |
| API calls timing out | Port 8080 not allowd | Add rule for Port 8080 from 10.0.0.0/8 |
