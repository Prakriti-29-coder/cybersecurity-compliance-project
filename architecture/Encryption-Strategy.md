# Encryption Strategy

## Overview

To improve data security in the cloud environment, encryption was implemented for both stored data and network communication. AWS KMS was used to manage encryption keys securely.

---

## KMS Configuration

A customer-managed KMS key was created for encrypting AWS resources used in the project.

### Key Details

- Key Alias: cybersecurity-project-key
- Key Type: Symmetric
- Automatic Rotation: Enabled annually
- Key Management Service: AWS KMS

The KMS key was used with multiple AWS services including S3, RDS, and EBS volumes.

---

# Data Classification

The project data was divided into different categories based on sensitivity.

## Level 1 — Public Data
This includes non-sensitive content such as public website information.

Examples:
- Static website pages
- Public documentation

Encryption for this type of data is optional but can still be applied for integrity purposes.

---

## Level 2 — Internal Data
This category contains internal organizational information.

Examples:
- Internal reports
- Team documentation

Security Applied:
- AES-256 encryption at rest
- TLS 1.2+ encryption during transmission

---

## Level 3 — Confidential Data
Sensitive business information falls under this category.

Examples:
- Customer records
- Financial information

Security Applied:
- KMS encryption enabled
- TLS 1.3 for secure communication
- Restricted IAM access

---

## Level 4 — Restricted Data
Highly sensitive information requiring maximum protection.

Examples:
- Encryption keys
- Password-related information

Security Applied:
- Hardware-backed key protection
- MFA for privileged access
- Audit logging enabled

---

# Encryption at Rest

## S3 Storage Encryption

S3 buckets were configured with server-side encryption using AWS KMS.

### Security Measures
- Public access blocked
- Versioning enabled
- Encryption enabled by default

---

## RDS Database Encryption

The RDS MySQL database was encrypted using the same KMS key.

### Security Features
- Encrypted storage
- Encrypted backups
- Restricted subnet access

---

## EBS Volume Encryption

EBS volumes attached to EC2 instances were encrypted to protect stored data.

### Features
- AES-256 encryption
- KMS-managed keys
- Automatic encryption during volume creation

---

# Encryption in Transit

To secure data while moving across the network, encrypted communication protocols were enforced.

## Implemented Controls

- HTTPS enabled
- TLS 1.2 or higher enforced
- SSL/TLS used for database connections
- AWS Certificate Manager used for certificates

---

# Key Access Control

Access to encryption keys was restricted using IAM permissions.

### Security Controls
- Only authorized services and users can decrypt data
- CloudTrail logs all KMS activity
- Keys cannot be exported outside AWS

---

# Compliance Support

The encryption strategy supports basic compliance requirements from:

- ISO 27001
- NIST Cybersecurity Framework

Implemented controls help improve confidentiality, integrity, and secure key management within the AWS environment.

---

# Summary

Encryption was applied across storage, databases, and network communication to improve security in the cloud infrastructure. AWS KMS was used for centralized key management with logging, rotation, and access control enabled.