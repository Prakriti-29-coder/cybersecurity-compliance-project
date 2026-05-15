# Threat Model

## Threats Identified

| Threat | Risk | Mitigation |
|---|---|---|
| Unauthorized Access | High | IAM + MFA |
| Data Breach | Critical | KMS Encryption |
| Malware | High | GuardDuty |
| SQL Injection | High | Security Groups |
| DDoS Attack | Medium | AWS Shield |
| Credential Theft | High | IAM Policies |

---

# Trust Boundaries

1. Internet to Web Tier
2. Web Tier to App Tier
3. App Tier to Database Tier

---

# Security Controls

- Network segmentation
- Least privilege access
- Encryption
- Monitoring
- Logging