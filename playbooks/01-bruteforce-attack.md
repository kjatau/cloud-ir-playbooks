# Playbook 01 — Brute Force Attack Detected

**Trigger:** AWS GuardDuty finding — UnauthorizedAccess:IAMUser/InstanceCredentialExfiltration

**Severity:** HIGH

**Response time target:** 15 minutes


---

## Step 1 — Triage (first 5 minutes)
- Go to AWS Console → GuardDuty → Findings
- Note the affected IAM user, source IP address, and time of alert
- Check if this is a known IP (internal test, pen test scheduled, etc.)
- If unknown IP — treat as real attack and proceed immediately

## Step 2 — Contain (next 10 minutes)
Disable the affected IAM user immediately:
Revoke all active sessions:
Deny all permissions immediately:
## Step 3 — Investigate
Check CloudTrail for everything this user did in the last 24 hours:
- Look for: unusual API calls, data downloads, new users created, permission changes

## Step 4 — Recover
- Create fresh credentials for the legitimate user
- Enable MFA if not already on
- Review and tighten the IAM policy
- Check if any data was accessed or exfiltrated

## Step 5 — Document
Write an incident summary covering:
- What happened and when
- What was affected
- How it was contained
- What was changed to prevent recurrence
