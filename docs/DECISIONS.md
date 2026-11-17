# Decisions

| # | Decision | Reason |
| --- | ---------- | -------- |
| 1 | AWS only, region ap-south-1 | One cloud, depth over breadth |
| 2 | Terraform 1.11 or newer | S3 native state locking, no DynamoDB table |
| 3 | Public repo named GatePass | Environment approvals on the GitHub free plan need it |
| 4 | Lambda container image as deploy target | Near-zero cost, no always-on resources |
| 5 | Three roles: plan, build, apply | Each job gets only the access it needs |
| 6 | AWS resource prefix `gatepass-` (lowercase) | Easy to find, tag, and clean up |
| 7 | Banned: EC2, Fargate, ALB, NAT gateway, RDS | Hourly billing burns credits |
| 8 | `main` protected by a ruleset: pull request required, no force-push, no deletion; approvals set to 0 | Solo developer, GitHub won't let you approve your own pull request |
