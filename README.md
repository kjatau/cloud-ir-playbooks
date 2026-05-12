# Cloud Incident Response Playbooks

Step-by-step incident response playbooks for AWS security alerts.
Built for security teams responding to GuardDuty, CloudTrail, and IAM alerts.

## Playbooks
- [01 — Brute Force Attack Detected](playbooks/01-bruteforce-attack.md)
- [02 — Exposed S3 Bucket Detected](playbooks/02-exposed-s3-bucket.md)
- [03 — Root Account Login Detected](playbooks/03-root-account-used.md)
- [04 — Suspicious API Activity Detected](playbooks/04-suspicious-api-calls.md)
- [05 — Crypto Mining Activity Detected](playbooks/05-crypto-mining.md)

## How to use
Each playbook covers:
- Trigger condition
- Severity and response time target
- Triage steps
- Containment commands
- Investigation steps
- Recovery actions
- Documentation requirements

## Tools referenced
- AWS GuardDuty
- AWS CloudTrail
- AWS IAM
- AWS EC2
- AWS S3