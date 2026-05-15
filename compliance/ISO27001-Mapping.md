# ISO 27001 Mapping

This document shows how different AWS security services used in the project support selected ISO 27001 security controls.

| ISO 27001 Control Area | AWS Service / Implementation |
|---|---|
| Access Control | AWS IAM |
| Cryptography and Encryption | AWS KMS |
| Logging and Audit Trails | AWS CloudTrail |
| Monitoring and Alerting | Amazon CloudWatch |
| Threat Detection | Amazon GuardDuty |
| Backup and Recovery | Amazon RDS Backups |
| Network Security | Security Groups and VPC |

---

# Security Controls Implemented

## Access Control
IAM users and roles were configured using least privilege principles to limit unnecessary access.

---

## Cryptography
AWS KMS was used to manage encryption keys for protecting stored data and backups.

---

## Logging and Monitoring
CloudTrail and CloudWatch were enabled to monitor account activity, API calls, and security-related events.

---

## Threat Detection
GuardDuty was enabled to detect suspicious activities and potential threats in the AWS environment.

---

## Backup Protection
Automated RDS backups were configured to improve data recovery capabilities.

---

## Network Security
Security Groups and subnet segmentation were used to control traffic between application layers.

---

# Compliance Summary

The project environment includes several security controls aligned with ISO 27001 practices, including:

- Least privilege access control
- Encryption for sensitive resources
- Continuous logging and monitoring
- Threat detection and alerting
- Network-level access restrictions
- Backup and recovery support

These configurations help improve the security and compliance readiness of the AWS infrastructure.