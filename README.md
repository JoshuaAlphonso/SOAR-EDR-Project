# SOAR-EDR-Project
## 📌 Project Summary & Objective
A simple security automation project using LimaCharlie, Tines, Slack, Email and Lazagne (Credential Dumper).
<br> This project demonstrates a security automation workflow integrating Tines with LimaCharlie to detect, respond to, and remediate threats in real-time.

- 📁 EDR Detection → 🎯 SOAR Playbook → 🔧 Remediation
- 🚀 Reduced response time from 15 minutes to under 2 minutes
- 🔄 Fully automated workflow with logging and rollback

# Diagram
![Alt Text](https://i.imgur.com/m35AdST.jpeg)

## ⚙️ How It Works (Quick Version)

1. EDR(limacharlie) detects suspicious activity.
2. Alert sent via webhook to SOAR(tines).
3. SOAR(tines) playbook triggers:
    - Fetch IP/domain reputation
    - Contain host (EDR API)
    - Notify SOC via Slack & Email
4. Analyst approves full remediation or rollback.

## 🚀 Demo
1. Executing a credential dumping payload to trigger the EDR alert based on preconfigured detection rules.
![Alt Text](https://i.imgur.com/j7zOZGl.png)
2. After executing LaZagne, alerts are automatically generated and sent via Slack and email.
<br>**Tines**
![Alt Text](https://i.imgur.com/4GpiN2U.png)
**Email**
![Alt Text](https://i.imgur.com/NfJ3KX7.png)

## 💡 Lessons Learned
- Real-world automation requires balancing **speed vs accuracy**
- SOAR customization is key to avoid false positives
- API rate limits and error handling matter a lot
