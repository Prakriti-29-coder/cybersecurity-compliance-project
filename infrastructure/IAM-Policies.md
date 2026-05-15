# IAM Configuration

## Users Created
- dev-user: EC2 Full + S3 ReadOnly
- security-admin: SecurityAudit + CloudTrail

## Roles Created
- ec2-instance-role: SSM Managed Instance Core

## Security Groups
- web-tier-sg: HTTP/HTTPS from anywhere
- app-tier-sg: App traffic from web tier only
- db-tier-sg: Database from app tier only