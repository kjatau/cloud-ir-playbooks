# Playbook 03 — Root Account Login Detected

**Trigger:** AWS CloudTrail — ConsoleLogin event from root account

**Severity:** CRITICAL

**Response time target:** 5 minutes

---

## Step 1 — Triage (first 2 minutes)
- Go to AWS Console → CloudTrail → Event history
- Filter by Event name: ConsoleLogin
- Check the source IP address — is it yours?
- Check the time — did you log in then?

## Step 2 — Contain (next 3 minutes)
If the login was NOT you — immediately:
- Change the root account password
- Remove all root account access keys:
- Contact AWS Support if you suspect full account compromise

## Step 3 — Investigate
Check everything root did during the session:
- Look for: new IAM users created, permissions changed, billing changes, new access keys

## Step 4 — Recover
- Enable MFA on root account immediately if not already on
- Remove all root access keys permanently
- Create a strong unique password for root
- Lock root credentials away — only use for billing emergencies

## Step 5 — Document
- Was this an authorized login or a breach?
- What actions were taken during the session?
- What controls were added to detect future root usage?

---

## Prevention rule
Root account should NEVER be used for daily work.
Always use IAM users with least privilege instead.
