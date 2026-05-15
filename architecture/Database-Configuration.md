# Database Configuration

## RDS Setup

For this project, an Amazon RDS MySQL database was configured inside private subnets so that it is not directly accessible from the internet.

### Configuration Details

- Database Engine: MySQL 8.0
- Instance Type: db.t3.micro
- DB Identifier: secure-database
- Storage Encryption: Enabled using AWS KMS
- Backup Retention: 30 days
- Availability: Multi-AZ deployment enabled
- Network Placement: Private database subnet

## Security Configuration

The database was secured using a dedicated security group named `db-tier-sg`.

### Access Rules
- Database access allowed only from the application tier
- Public access disabled
- MySQL port 3306 restricted internally

### Authentication
- Master Username: admin
- Strong password configured during setup

## Additional Security Measures

- Automated backups enabled
- Database traffic restricted using security groups
- Encryption enabled for data at rest
- Monitoring enabled through CloudWatch

## Summary

The database layer was designed following basic cloud security best practices. The RDS instance was isolated inside private subnets with restricted access controls and encryption enabled to improve security and compliance.