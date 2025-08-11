# FusionSOC–NIST

Controls used to help mitigate FusionSOC with **NIST SP 800-53 Rev.5** and **NIST CSF** mappings.

## Structure
- kql
- detections
- controls
- policies
- docs

**Updated:** 2025-08-10


**Controls Put in Place** 

**AC-7 (Unsuccessful Logon Attempts)**

≥5 Windows 4625 in <15m → incident; AWS ConsoleLogin failures correlated by user/IP; lockout policy/GPO screenshot.
 
 <img width="423" height="566" alt="Screenshot 2025-08-09 120837" src="https://github.com/user-attachments/assets/f35ad327-b7e7-44c4-9e58-a841e6722fe5" />
 <img width="1321" height="647" alt="Failed logon AWS " src="https://github.com/user-attachments/assets/088937c5-7daa-4c0f-bf99-94f549c70f3a" />
 <img width="1339" height="652" alt="AWS Detection rule failed logon" src="https://github.com/user-attachments/assets/20896e0f-a862-472a-97a5-c62ddc4750a7" />
 - <img width="1329" height="640" alt="Successful and Unsuccessful logon attempts" src="https://github.com/user-attachments/assets/706a8842-191f-4f16-9249-b555e39f3406" />

 AC-7 Control is important because it Monitors for bursts of failed sign-ins (e.g., ≥5 Windows 4625 events in 15 minutes and AWS ConsoleLogin failures) and raises an incident, grouped by account/host/IP.Catches brute-force/password-spray early. Repeated failures are a classic precursor to compromise.
Reduces attacker dwell time. Fast alerts let you lock the account or block the source before a successful guess.
Protects high-value identities. Correlating by user and source IP highlights targeted accounts.


**AC-2 (Account Management)**

AWS CreateUser/DeleteUser → Sentinel alert → incident shows target user → automation assigns owner.

<img width="1353" height="500" alt="Screenshot 2025-08-09 134031" src="https://github.com/user-attachments/assets/62c3182a-4d8d-40b3-96b4-8e34c1e7dc2f" />
<img width="1346" height="645" alt="Delete users AWS" src="https://github.com/user-attachments/assets/06fcffee-79f6-47b9-9257-847c07f03a97" />
- <img width="1354" height="681" alt="Screenshot 2025-08-09 134604" src="https://github.com/user-attachments/assets/cdea4e05-0486-49ba-8b07-776983720791" />
  <img width="1352" height="639" alt="IAM detetction rule" src="https://github.com/user-attachments/assets/787ee32e-26de-4597-8f92-310117d2374e" />

This Control is important because 
AC-2 ensures you tightly govern the full lifecycle of identities—creation, modification, disabling, and deletion—so only the right people have the right access at the right time. It reduces risk from stale accounts and privilege creep, strengthens auditability for compliance, and provides clear hooks for detections

**SI-4 (System Monitoring) This Control Covers Command line activity**

 Execute Powershell command
- <img width="1095" height="337" alt="Powershell command generate logs" src="https://github.com/user-attachments/assets/7d31a064-f40c-4c11-bc16-6706924ebee8" />

This Control helps  makes sure your environment is continuously observed for suspicious activity—not just logging, but collecting, analyzing, and acting on signals.

**Phishing emails multiple controls can be of use i'll just name a few.**

**SI-4 – System Monitoring :  Sentinel rules that detect brand-impersonation, suspicious links, and anomalous sender.**

**IR-4 – Incident Handling: Automation rules/playbooks to quarantine messages, notify users, enrich with VirusTotal, and assign an owner.**

**SI-3 – Malicious Code Protection: Email security gateway / AV scanning of attachments and URLs (detonation/sandboxing).**

**AT-2 – Security Awareness Training: Simulated phishing and just-in-time user education to reduce click-through.**

<img width="1360" height="767" alt="Suspicious email" src="https://github.com/user-attachments/assets/b1548447-bdeb-4441-9576-7cbadc34f0d5" />

<img width="1333" height="636" alt="Virustotal" src="https://github.com/user-attachments/assets/7c32d8a2-538c-4f8b-aa60-037c061e6e4e" />


**Author:** Dareis Newton — Winston‑Salem, NC  
**Updated:** 2025-08-10

