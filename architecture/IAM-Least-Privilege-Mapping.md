# IAM Least Privilege Mapping

## Overview

This document explains the IAM users, roles, and security controls configured for the cybersecurity compliance project. The setup follows the principle of least privilege, where users and services are given only the permissions required for their tasks.

---

# Principle of Least Privilege

The main goal of this approach is to reduce unnecessary access and improve overall cloud security. Permissions were assigned carefully to avoid excessive privileges.

---

# IAM Users and Roles

## 1. dev-user

### Purpose
This user was created for development and testing activities within the AWS environment.

### Permissions Assigned

#### AmazonEC2FullAccess
Allows the user to:
- Launch and manage EC2 instances
- Start or stop instances
- Configure networking components related to EC2

#### AmazonS3ReadOnlyAccess
Allows the user to:
- View S3 buckets
- Download files from S3
- Access stored objects in read-only mode

### Restrictions
The user does not have permission to:
- Delete production databases
- Modify IAM policies or roles
- Access security audit logs
- Perform sensitive administrative actions

---

## 2. security-admin

### Purpose
This user is responsible for monitoring security events and reviewing AWS audit logs.

### Permissions Assigned

#### SecurityAudit
Allows:
- Viewing AWS configurations
- Reviewing security settings
- Monitoring account activity

#### CloudTrailFullAccess
Allows:
- Viewing CloudTrail logs
- Managing CloudTrail trails
- Investigating API activity

### Restrictions
The user cannot:
- Delete infrastructure resources
- Modify production systems
- Access application data directly

---

## 3. ec2-instance-role

### Purpose
This IAM role is attached to EC2 instances so they can securely interact with AWS services.

### Permissions Assigned

#### AmazonSSMManagedInstanceCore
Allows:
- Systems Manager access
- Patch management
- Session Manager connectivity
- CloudWatch integration

### Restrictions
The role cannot:
- Access other AWS accounts
- Modify unrelated resources
- Delete infrastructure components

---

# Network-Level Access Control

Security Groups were configured to control communication between different layers of the architecture.

---

## Web Tier Security Group (`web-tier-sg`)

### Inbound Rules
- HTTP (Port 80) allowed from the internet
- HTTPS (Port 443) allowed from the internet

### Security Controls
- All other inbound traffic blocked
- Database access not allowed directly

---

## Application Tier Security Group (`app-tier-sg`)

### Inbound Rules
- Port 8080 allowed only from the web-tier security group

### Security Controls
- No direct public internet access
- Restricted communication with other layers

---

## Database Tier Security Group (`db-tier-sg`)

### Inbound Rules
- MySQL Port 3306 allowed only from the application tier

### Security Controls
- Public access disabled
- Only internal application servers can connect

---

# Access Review Process

To maintain security, permissions and configurations should be reviewed regularly.

| Review Type | Frequency |
|---|---|
| User Permission Review | Monthly |
| Security Group Audit | Quarterly |
| Full Access Review | Annually |

---

# Audit and Monitoring

AWS CloudTrail was enabled to record account activity and API usage.

The logs help track:
- Which user accessed resources
- What actions were performed
- When activities occurred
- Whether actions were successful or denied

These logs support monitoring, troubleshooting, and compliance requirements.

---

# Summary

IAM users, roles, and security groups were configured using least privilege principles to improve cloud security. Access was restricted wherever possible, and logging was enabled to support monitoring and auditing within the AWS environment.