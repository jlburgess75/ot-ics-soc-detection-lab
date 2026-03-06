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

- Exclude known administrative scripts
- Exclude approved automation accounts
- Baseline normal PowerShell activity in the environment
- Monitor for unusual encoded command usage patterns
