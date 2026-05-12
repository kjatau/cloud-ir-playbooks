# Playbook 04 — Suspicious API Activity Detected

**Trigger:** AWS CloudTrail — unusual API calls detected

**Severity:** HIGH

**Response time target:** 15 minutes

---

## Step 1 — Triage (first 5 minutes)
- Go to AWS Console → CloudTrail → Event history
- Look for these red flag API calls:
  - CreateUser
  - AttachUserPolicy
  - CreateAccessKey
  - PutBucketPolicy
  - DeleteTrail
  - StopLogging
- Note the IAM user, source IP, and time

## Step 2 — Contain (next 10 minutes)
If the activity looks malicious, disable the user immediately:
If CloudTrail was stopped — restart it immediately:
Block the suspicious IP at the VPC level:
## Step 3 — Investigate
Get full list of API calls from the suspicious user:
- Did they create new users or access keys?
- Did they access or download sensitive data?
- Did they try to cover their tracks by deleting logs?

## Step 4 — Recover
- Rotate all access keys for affected users
- Review all IAM policies for unauthorized changes
- Re-enable any disabled security controls
- Scan all S3 buckets for policy changes

## Step 5 — Document
- Full timeline of suspicious API calls
- What was accessed or changed
- How the attacker got in
- What was fixed and what monitoring was added
