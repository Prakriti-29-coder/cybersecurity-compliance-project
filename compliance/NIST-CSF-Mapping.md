# NIST Cybersecurity Framework Mapping

This document explains how the AWS services configured in the project align with the core functions of the NIST Cybersecurity Framework (CSF).

| NIST Function | AWS Services Used |
|---|---|
| Identify | IAM, CloudTrail |
| Protect | AWS KMS, Security Groups |
| Detect | GuardDuty, CloudWatch |
| Respond | SNS Alerts, Incident Response Process |
| Recover | RDS Backups, Snapshots |

---

# NIST Security Functions

## 1. Identify

The Identify function focuses on understanding and managing cloud resources, users, and security risks.

### Implemented Controls
- IAM used for user and role management
- CloudTrail enabled for tracking AWS account activity
- Resource monitoring through AWS services

This helps maintain visibility into who is accessing resources and what actions are being performed.

---

## 2. Protect

The Protect function focuses on preventing unauthorized access and securing sensitive data.

### Implemented Controls
- AWS KMS used for encryption key management
- Security Groups configured as virtual firewalls
- Private subnets used for sensitive resources
- Least privilege access applied through IAM

These controls help reduce exposure to common security risks.

---

## 3. Detect

The Detect function helps identify suspicious activity and security incidents.

### Implemented Controls
- GuardDuty enabled for threat detection
- CloudWatch used for monitoring and alerting
- VPC Flow Logs enabled for traffic analysis

The environment can generate alerts when unusual activity is detected.

---

## 4. Respond

The Respond function focuses on handling and managing security incidents effectively.

### Implemented Controls
- Incident response procedures documented
- SNS alerts configured for notifications
- CloudTrail logs used for investigation and analysis

These measures help support quick response and investigation during security events.

---

## 5. Recover

The Recover function ensures that systems and data can be restored after a failure or security incident.

### Implemented Controls
- Automated RDS backups enabled
- Database snapshots supported
- Recovery options available through AWS services

This helps improve business continuity and recovery capabilities.

---

# Summary

The project environment was designed with security controls that align with the main functions of the NIST Cybersecurity Framework. AWS services such as IAM, KMS, CloudTrail, GuardDuty, and CloudWatch were used to support identification, protection, detection, response, and recovery processes within the cloud infrastructure.