# Detection: Suspicious Outbound Network Connection by Process

## Purpose

Detect suspicious outbound network connections initiated by unusual or high-risk processes.

## Risk

Attackers often establish outbound connections for command-and-control (C2) communication after gaining access to a system.

## Data Source

Sysmon Event ID 3 – Network Connection

---

## SPL Query

index=sysmon EventCode=3 Image!="*chrome.exe*" Image!="*msedge.exe*"

---

## MITRE ATT&CK

T1071 – Application Layer Protocol

---

## Investigation Steps

1. Identify the process initiating the network connection.
2. Determine the user account running the process.
3. Review the destination IP address and port.
4. Investigate whether the destination is known or suspicious.
5. Examine additional activity from the host.
6. Determine whether the activity indicates command-and-control communication.

---

## Tuning Notes

To reduce false positives:

- Exclude common browser processes
- Exclude approved enterprise applications
- Baseline normal outbound connections
- Monitor for connections to unknown external IP addresses
