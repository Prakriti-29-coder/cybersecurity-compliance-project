# Cybersecurity & Compliance Implementation on AWS

## Project Overview
This project demonstrates the implementation of a secure cloud infrastructure on AWS following cybersecurity best practices and compliance standards such as ISO 27001 and the NIST Cybersecurity Framework.

The project focuses on:
- Identity and Access Management (IAM)
- Network security and segmentation
- Encryption and key management
- Logging and monitoring
- Incident response planning
- Security compliance mapping
- SOC dashboard monitoring

---

# Architecture Summary

A secure 3-tier cloud architecture was designed using AWS services.

## Network Layers
- Public Web Tier
- Private Application Tier
- Private Database Tier

## Security Controls
- VPC isolation
- Public and private subnets
- Security Groups (virtual firewalls)
- IAM least privilege access
- KMS encryption
- CloudTrail audit logging
- VPC Flow Logs
- CloudWatch monitoring dashboards

---

# AWS Services Used

| Service | Purpose |
|---|---|
| Amazon VPC | Network isolation |
| Security Groups | Firewall and traffic filtering |
| IAM | Access control and least privilege |
| AWS KMS | Encryption and key management |
| Amazon S3 | Secure object storage |
| Amazon RDS | Managed MySQL database |
| CloudTrail | Audit logging |
| CloudWatch | Monitoring and dashboards |
| VPC Flow Logs | Network traffic logging |
| SNS | Alert notifications |
| EC2 | Web/Application server hosting |

---

# Project Features

## IAM Least Privilege Mapping
- IAM users and roles configured
- Role-based access control implemented
- Access review strategy documented

## Network Security
- 3-tier segmented architecture
- Restricted communication between layers
- Security groups enforce minimum required access

## Encryption Strategy
- Data at rest encrypted using AWS KMS
- TLS/HTTPS designed for secure communication
- Encrypted RDS storage and backups

## Key Management
- Customer-managed KMS key created
- Automatic key rotation enabled
- Access controlled through IAM policies

## Logging & Monitoring
- CloudTrail enabled for API auditing
- VPC Flow Logs configured
- CloudWatch dashboard for monitoring
- SNS alerts for security events

## Incident Response
- Six-phase incident response lifecycle documented
- Detection, containment, eradication, and recovery procedures included

## Compliance Mapping
- ISO 27001 control alignment
- NIST Cybersecurity Framework mapping

---

# Repository Structure

```text
architecture/
compliance/
incident-response/
infrastructure/
soc-dashboards/
threat-models/