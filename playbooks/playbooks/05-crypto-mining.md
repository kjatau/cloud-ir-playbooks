# Playbook 05 — Crypto Mining Activity Detected

**Trigger:** AWS GuardDuty finding — CryptoCurrency:EC2/BitcoinTool.B

**Severity:** HIGH

**Response time target:** 10 minutes

---

## Step 1 — Triage (first 3 minutes)
- Go to AWS Console → GuardDuty → Findings
- Note the affected EC2 instance ID, IP address, and time
- Check which AWS account and region it is in
- Check who owns that EC2 instance

## Step 2 — Contain (next 7 minutes)
Isolate the infected EC2 instance immediately:
Stop the instance:
Remove it from any load balancers and auto scaling groups so it stops serving traffic.

## Step 3 — Investigate
Check CloudTrail for how the attacker got in:
- Was there an exposed port or weak password?
- Were any new IAM roles or access keys created?
- How long has mining been running — check your AWS bill

## Step 4 — Recover
- Terminate the infected instance — do not restart it
- Launch a fresh clean instance from a trusted AMI
- Patch the vulnerability that allowed entry
- Review all security groups for exposed ports
- Set up AWS Cost Anomaly Detection to catch unexpected bills early

## Step 5 — Document
- How the attacker got in
- How long mining was running
- Estimated cost impact on AWS bill
- What ports or vulnerabilities were closed
- What monitoring was added to detect it faster next time

---

## Prevention rules
- Never expose port 22 (SSH) to 0.0.0.0/0
- Always use SSH key pairs, never passwords
- Enable GuardDuty on all AWS accounts and regions
- Set up AWS Cost Anomaly Detection alerts