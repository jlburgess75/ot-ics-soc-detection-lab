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
