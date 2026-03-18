
# Brute Force Attack Screenshots

This folder contains screenshots that demonstrate **RDP Brute Force (Port 3389)** and **SMB Brute Force (Port 445)** attack scenarios.  
The images provide visual evidence of how repeated authentication attempts are executed against the Windows victim machine and how these attempts are captured in both Windows Security and Sysmon logs.

The screenshots highlight:
- Failed and successful login attempts (Event IDs 4625 and 4624)
- Privileged logons and credential usage (Event IDs 4672, 4648)
- Network connections recorded during brute force activity (Sysmon Event ID 3)

These visual records help SOC analysts quickly understand the attack flow and correlate authentication failures with network activity.
