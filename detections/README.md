# Detection Engineering

This directory contains Splunk detection rules used in the SOC detection lab.

Each detection includes:

- Detection objective
- SPL query
- MITRE ATT&CK mapping
- Investigation guidance
- Tuning considerations

---

## Current Detections

| Detection | Purpose |
|----------|---------|
| powershell_encoded_command | Detects encoded PowerShell execution often used by attackers |
| suspicious_outbound_by_process | Detects unusual outbound connections initiated by suspicious processes |
| registry_runkey_persistence | Detects persistence via Windows Run registry keys |

---

## Detection Development Methodology

Each detection follows a structured workflow:

1. Identify attacker behavior
2. Identify telemetry source
3. Write detection logic
4. Test detection in lab environment
5. Reduce false positives
6. Document investigation steps

---

## Detection Lifecycle

```text
Telemetry
↓
Detection Rule
↓
Alert
↓
SOC Investigation
↓
Incident Documentation
