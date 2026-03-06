# Detection: PowerShell Encoded Command Execution

## Purpose

Detect attackers executing encoded PowerShell commands to hide malicious activity.

## Risk

Encoded PowerShell is commonly used for obfuscation, malware delivery, downloader activity, and post-exploitation.

## Data Source

Sysmon Event ID 1 – Process Creation

## SPL Query

```spl
index=sysmon EventCode=1 Image="*powershell.exe*" CommandLine="*encoded*"
## MITRE ATT&CK

T1059.001 – PowerShell

---

## Investigation Steps

1. Identify the user who executed the PowerShell command.
2. Review the parent process that launched PowerShell.
3. Examine the full command line for encoded payloads.
4. Check for additional processes spawned afterward.
5. Investigate network connections originating from the same host.
6. Determine whether the activity was legitimate administrative activity.

---

## Tuning Notes

To reduce false positives:

• Exclude known administrative scripts  
• Exclude automation accounts  
• Baseline normal PowerShell usage within the environment
