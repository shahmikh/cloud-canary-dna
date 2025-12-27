# 🟣 Cloud Canary DNA

**Cloud Canary DNA** is a deception-based cloud security project that creates **fake but realistic IAM identities** to detect attackers early.

Instead of waiting for damage, this project detects threats **when an attacker touches a canary identity or resource**.

---

##  What This Project Does

- Creates fake IAM users that look like real humans
- Simulates:
  - Logins
  - Routine API activity
  - Time-based work behavior
- Monitors CloudTrail logs
- Triggers **email alerts** when:
  - Canary identity is used outside normal hours
  - Suspicious access is detected

---

##  Why This Matters

Attackers often:
- Hunt for unused IAM users
- Steal access keys
- Operate at odd hours

This project uses **deception + behavior**, not signatures.

Any interaction with the canary = **high-confidence alert**.

---

##  Tech Stack

- AWS IAM
- AWS CloudTrail (Management + Data Events)
- AWS SNS (Email Alerts)
- Python (boto3)
- Linux (CentOS)

---

##  Project Structure

cloud-canary-dna/
├── src/
│ ├── create_canary_user.py
│ ├── human_login_behavior.py
│ ├── human_routine_behavior.py
│ └── detect_canary_activity.py
├── logs/
│ └── sample_cloudtrail.json
├── docs/
│ └── day2-step2-s3-data-events.md
├── README.md
├── requirements.txt
└── .gitignore


---

##  Alerting Flow

1. Canary IAM user performs normal behavior
2. CloudTrail logs activity
3. Detection script analyzes events
4. If behavior is suspicious:
   - 🚨 Email alert is sent via SNS

---

##  Proof of Work

Screenshots included:
- Canary IAM user
- CloudTrail Data Events
- Detection alert in terminal
- Email alert received

---

##  Future Improvements

- Real-time detection using EventBridge
- Lambda-based alerting
- Multiple canary identities
- Geo-location based alerts

---

##  Author

Built by **shahmikh**  
Focused on cloud security, detection engineering, and threat intelligence.

