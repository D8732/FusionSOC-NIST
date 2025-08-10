# FusionSOC–NIST

Extend FusionSOC with **NIST SP 800-53 Rev.5** and **NIST CSF** mappings.

## Structure
- kql
- detections
- controls
- evidence
- workbooks
- playbooks
- policies
- docs

**Updated:** 2025-08-10


Controls Put in Place 
AC-7 (Unsuccessful Logon Attempts)
≥5 Windows 4625 in <15m → incident; AWS ConsoleLogin failures correlated by user/IP; lockout policy/GPO screenshot.
 
 <img width="423" height="566" alt="Screenshot 2025-08-09 120837" src="https://github.com/user-attachments/assets/f35ad327-b7e7-44c4-9e58-a841e6722fe5" />
 <img width="1321" height="647" alt="Failed logon AWS " src="https://github.com/user-attachments/assets/088937c5-7daa-4c0f-bf99-94f549c70f3a" />
 <img width="1339" height="652" alt="AWS Detection rule failed logon" src="https://github.com/user-attachments/assets/20896e0f-a862-472a-97a5-c62ddc4750a7" />

 This Control is important because it Monitors for bursts of failed sign-ins (e.g., ≥5 Windows 4625 events in 15 minutes and AWS ConsoleLogin failures) and raises an incident, grouped by account/host/IP.
 Catches brute-force/password-spray early. Repeated failures are a classic precursor to compromise.

Reduces attacker dwell time. Fast alerts let you lock the account or block the source before a successful guess.

Protects high-value identities. Correlating by user and source IP highlights targeted accounts.


AC-2 (Account Management)
AWS CreateUser/DeleteUser → Sentinel alert → incident shows target user → automation assigns owner.

<img width="1353" height="500" alt="Screenshot 2025-08-09 134031" src="https://github.com/user-attachments/assets/62c3182a-4d8d-40b3-96b4-8e34c1e7dc2f" />
<img width="1346" height="645" alt="Delete users AWS" src="https://github.com/user-attachments/assets/06fcffee-79f6-47b9-9257-847c07f03a97" />
- <img width="1354" height="681" alt="Screenshot 2025-08-09 134604" src="https://github.com/user-attachments/assets/cdea4e05-0486-49ba-8b07-776983720791" />
  <img width="1352" height="639" alt="IAM detetction rule" src="https://github.com/user-attachments/assets/787ee32e-26de-4597-8f92-310117d2374e" />
