# Incident Report Template

This template can be used to document security incidents detected within the AWS environment. Proper documentation helps during investigation, recovery, and future security improvements.

---

# Incident Details

| Field | Information |
|---|---|
| Incident ID | |
| Date and Time | |
| Severity Level | |
| Reported By | |
| Current Status | |

---

# Incident Description

Provide a brief summary of the incident.

Example:
- Unauthorized login attempt detected
- Suspicious API activity observed
- Unexpected network traffic identified

Include details about:
- What happened
- How it was detected
- Which systems were affected

---

# Affected Resources

List all impacted AWS resources or services.

Examples:
- EC2 Instances
- S3 Buckets
- RDS Database
- IAM Users or Roles
- Security Groups

---

# Incident Timeline

| Time | Activity / Observation |
|---|---|
| | |
| | |
| | |

Document important events in chronological order.

---

# Actions Taken

Describe the steps performed during the response process.

Possible actions:
- Detection and investigation
- Isolation of affected resources
- Blocking suspicious IP addresses
- Disabling compromised credentials
- Restoring backups
- Re-enabling services after verification

---

# Root Cause Analysis

Explain the reason behind the incident.

Examples:
- Weak IAM permissions
- Misconfigured security group
- Exposed credentials
- Unpatched vulnerability

---

# Recommendations and Improvements

List security improvements that can help prevent similar incidents in the future.

Examples:
- Improve monitoring and alerting
- Apply stricter firewall rules
- Rotate access keys regularly
- Enable MFA for IAM users
- Perform regular security audits

---

# Lessons Learned

Mention important observations or improvements identified after resolving the incident.

Examples:
- Faster alerting needed
- Logging should be reviewed more frequently
- Access policies need tighter restrictions

---

# Incident Closure

| Field | Information |
|---|---|
| Resolved By | |
| Resolution Date | |
| Final Status | Closed / Monitoring |
| Additional Notes | |

---

# Summary

This template helps maintain proper incident documentation and supports security monitoring, auditing, and compliance activities within the AWS environment.