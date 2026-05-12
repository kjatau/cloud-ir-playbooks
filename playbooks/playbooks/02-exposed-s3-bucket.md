# Playbook 02 — Exposed S3 Bucket Detected

**Trigger:** AWS Config or GuardDuty finding — S3 bucket made public

**Severity:** CRITICAL

**Response time target:** 5 minutes

---

## Step 1 — Triage (first 2 minutes)
- Go to AWS Console → S3 → find the flagged bucket
- Check what data is inside — is it sensitive?
- Check when it was made public and by who

## Step 2 — Contain (next 3 minutes)
Block all public access immediately:
## Step 3 — Investigate
Check who changed the bucket policy:
- Was it accidental or intentional?
- Was any sensitive data downloaded while it was public?

## Step 4 — Recover
- Review all bucket policies and ACLs
- Enable S3 server access logging
- Add bucket to your Terraform secure module going forward

## Step 5 — Document
- What data was exposed and for how long
- Who made the change
- What controls were added to prevent recurrence
