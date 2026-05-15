# Security Architecture Document

## Project Overview
- **Project Name**: Cybersecurity & Compliance Implementation
- **Date**: 2026-05-15
- **Student**: Prakrit Dey
- **AWS Region**: us-east-1

## Network Architecture

### VPC Details
- **VPC Name**: secure-vpc
- **VPC CIDR**: 10.0.0.0/16

### Subnets Created
#### Public Subnets (Web Tier)
- public-subnet-1: 10.0.1.0/24 (us-east-1a)
- public-subnet-2: 10.0.2.0/24 (us-east-1b)

#### Private Subnets (Application Tier)
- private-subnet-app-1: 10.0.10.0/24 (us-east-1a)
- private-subnet-app-2: 10.0.11.0/24 (us-east-1b)

#### Private Subnets (Database Tier)
- private-subnet-db-1: 10.0.20.0/24 (us-east-1a)
- private-subnet-db-2: 10.0.21.0/24 (us-east-1b)

### Internet Connectivity
- **Internet Gateway**: secure-igw
- **NAT Gateway**: [To be created if needed]
- **Route Tables**: Public route table configured for internet access

## Security Groups (Firewalls)

### Web Tier Security Group (web-tier-sg)
Allows:
- HTTP (port 80) from anywhere (0.0.0.0/0)
- HTTPS (port 443) from anywhere (0.0.0.0/0)
All other traffic: BLOCKED

### Application Tier Security Group (app-tier-sg)
Allows:
- Port 8080 from web-tier-sg ONLY
- All other sources: BLOCKED

### Database Security Group (db-tier-sg)
Allows:
- MySQL (port 3306) from app-tier-sg ONLY
- All other sources: BLOCKED

## Encryption

### KMS Master Key
- **Alias**: cybersecurity-project-key
- **Key Type**: Symmetric
- **Rotation**: Annual (automatic)
- **Key ID**: 9a6d7a32-937e-40f7-99c7-9c6dfa1ec965

### Data at Rest Encryption
- S3 buckets: KMS encryption
- RDS database: KMS encryption
- EBS volumes: KMS encryption (if applicable)

### Data in Transit Encryption
- All connections: TLS 1.2+
- Certificates: AWS Certificate Manager
- VPN: Available for remote access

## Access Control (IAM)

### Users
1. **dev-user**
   - EC2 Full Access
   - S3 Read-Only

2. **security-admin**
   - Security Audit role
   - CloudTrail Full Access

### Roles
1. **ec2-instance-role**
   - For EC2 instances
   - Systems Manager access

## Database Configuration

### RDS MySQL Instance
- **Identifier**: secure-database
- **Engine**: MySQL 8.0
- **Instance Type**: db.t3.micro
- **Storage**: 20 GB
- **Encryption**: KMS enabled
- **Backups**: 30-day retention
- **Multi-AZ**: Yes (failover instance in different AZ)
- **Subnet**: Private (db-tier only)

## Logging & Monitoring

### CloudTrail
- **Trail Name**: security-audit-trail
- **Log Destination**: S3 bucket (cloudtrail-logs)
- **Log File Validation**: Enabled
- **Coverage**: All API calls

### VPC Flow Logs
- **Log Group**: /aws/security/vpc-flow-logs
- **Filter**: All traffic (ACCEPT, REJECT)
- **Destination**: CloudWatch Logs

### GuardDuty
- **Status**: Enabled
- **Function**: Threat detection
- **Findings**: Real-time alerts

## Trust Boundaries
