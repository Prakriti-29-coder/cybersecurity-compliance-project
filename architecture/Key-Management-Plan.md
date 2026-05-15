# Key Management Plan

## Overview

This document describes how cryptographic keys were managed in the AWS cloud environment using AWS Key Management Service (KMS). The main objective was to securely handle encryption keys used for protecting storage, databases, and other cloud resources.

---

# Key Management Objectives

The key management process was designed to:

- Protect sensitive information
- Control access to encrypted resources
- Support secure encryption practices
- Maintain compliance with security standards

---

# AWS KMS Configuration

A customer-managed key was created in AWS KMS for this project.

| Configuration | Details |
|---|---|
| Key Alias | cybersecurity-project-key |
| Key Type | Symmetric |
| Key Rotation | Enabled annually |
| Service Used | AWS KMS |

The KMS key was integrated with AWS services such as S3, RDS, and EBS for encryption purposes.

---

# Key Lifecycle Management

The following stages were considered during key management:

## 1. Key Creation
The encryption key was created using AWS KMS as a customer-managed symmetric key.

## 2. Key Storage
Keys are securely stored and protected within AWS-managed infrastructure.

## 3. Key Usage
The key is used for encrypting and decrypting AWS resources including:
- S3 objects
- RDS database storage
- EBS volumes

## 4. Key Rotation
Automatic annual rotation was enabled to improve long-term security.

## 5. Key Revocation
Access permissions can be removed immediately if a user or service is compromised.

## 6. Key Deletion
Unused keys can be scheduled for deletion using AWS KMS procedures.

---

# Access Control

Access to encryption keys was restricted using IAM policies and permissions.

Only authorized users or services are allowed to:
- Encrypt data
- Decrypt data
- Manage key settings

Administrative access was limited to reduce security risks.

---

# Monitoring and Logging

AWS CloudTrail was enabled to monitor all KMS-related activity.

Logged events include:
- Key usage
- Encryption requests
- Decryption requests
- Permission changes

Monitoring helps detect suspicious activity and supports auditing requirements.

---

# Backup and Recovery

The environment supports encrypted backup strategies including:

- Encrypted RDS snapshots
- Backup protection using KMS
- Multi-region backup support where applicable

This helps maintain data availability during recovery scenarios.

---

# Security Best Practices Followed

The following security practices were implemented:

- Automatic key rotation enabled
- Least privilege access applied
- Encryption keys not hardcoded in applications
- Centralized key management using AWS KMS
- Monitoring enabled through CloudTrail

---

# Compliance Mapping

| Standard | Security Area |
|---|---|
| ISO 27001 | Key management and cryptography |
| NIST Cybersecurity Framework | Cryptographic protection controls |

---

# Summary

AWS KMS was used to securely manage encryption keys across the project infrastructure. Access control, monitoring, rotation, and backup protections were implemented to improve overall cloud security and support compliance requirements.