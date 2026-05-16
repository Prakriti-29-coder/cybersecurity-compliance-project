
## Compliance Mapping

### ISO 27001 Compliance
- Access Control (A.8): IAM roles with least privilege
- Cryptography (A.9): KMS encryption enabled
- Operations Security (A.11): CloudTrail logging
- Physical Security (A.10): AWS managed data centers
- Incident Management (A.15): Logging and monitoring

### NIST Framework
- Identify: Asset inventory via CloudTrail
- Protect: Security groups + encryption
- Detect: GuardDuty + CloudWatch + VPC Flow Logs
- Respond: Logging enables investigation
- Recover: RDS backups + Multi-AZ

## Summary
 3-tier network architecture implemented
 Security groups enforce least privilege
 Encryption at rest and in transit
 Comprehensive logging and monitoring
 Compliance-ready design
 High availability (Multi-AZ)