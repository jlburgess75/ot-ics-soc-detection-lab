# Detection: Registry Run Key Persistence

## Purpose

Detect persistence mechanisms where attackers add programs to Windows Run registry keys to execute automatically during system startup.

## Risk

Attackers commonly use registry Run keys to maintain persistence after initial compromise. This allows malicious programs to execute whenever the user logs in.

## Data Source

Sysmon Event ID 13 – Registry Value Set

---

## SPL Query

index=sysmon EventCode=13 TargetObject="*\\Software\\Microsoft\\Windows\\CurrentVersion\\Run*"

---

## MITRE ATT&CK

T1547.001 – Registry Run Keys / Startup Folder

---

## Investigation Steps

1. Identify the host where the registry modification occurred.
2. Determine the user account that performed the change.
3. Review the registry value added or modified.
4. Investigate the executable referenced in the registry key.
5. Check whether the executable is legitimate or suspicious.
6. Investigate additional activity from the same host.

---

## Tuning Notes

To reduce false positives:

- Exclude legitimate software installers
- Exclude approved enterprise applications
- Baseline normal Run key changes in the environment
- Investigate unexpected or unknown executables
