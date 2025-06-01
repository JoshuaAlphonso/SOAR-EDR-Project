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
- **1.** Executing a credential dumping payload to trigger the EDR alert based on preconfigured detection rules.
![Alt Text](https://i.imgur.com/j7zOZGl.png)
- **2.** After executing LaZagne, alerts are automatically generated and sent via Slack and email.
<br>**Slack:**
![Alt Text](https://i.imgur.com/4GpiN2U.png)
**Email:**
![Alt Text](https://i.imgur.com/NfJ3KX7.png)
- **3.** A prompt appears asking "Isolate the machine?". If "No" is selected, a follow-up alert is sent to slack indicating the system was not isolated and may be required for further investigations.
<br>**Prompt:**

![Alt Text](https://i.imgur.com/Dx2B7cB.png)
<br>**Slack:**
![Alt Text](https://i.imgur.com/qV2FOUr.png)
- **4.** If "Yes" is selected, a Slack message is generated confirming the alert details. The message includes the isolation status ("True") and the name of the machine being isolated.
<br>**Prompt:**

![Alt Text](https://i.imgur.com/vlR7qfM.png)
<br>**Slack:**
![Alt Text](https://i.imgur.com/Z2K4mjM.png)

- **5.** Although the machine appears to be connected to the internet, any outbound network requests (e.g., ping) result in "General Failure" indicating successful isolation within a sandboxed environment. 
<br>**Test Machine Connectivity Status:**
![Alt Text](https://i.imgur.com/SPX5Dk1.png)
- **6.** After successfully isolating the machine, you have the option to safely reintegrate it into the network once the threat has been remediated or the investigation is complete.
This showcases how quickly a SOAR system can respond to threats and how effectively the endpoint reacts to isolation, emphasizing the efficiency of automated incident response.
<br>**EDR Machine Status:** 

![Alt Text](https://i.imgur.com/1P1gIGl.png)

## 💡 Lessons Learned
- Real-world automation requires balancing **speed vs accuracy**
- SOAR customization is key to avoid false positives
- API rate limits and error handling matter a lot
