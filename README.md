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
