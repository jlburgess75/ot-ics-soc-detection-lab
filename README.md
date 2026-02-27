# OT / ICS SOC Detection Lab

Hybrid IT/OT detection lab that simulates an enterprise Active Directory environment with Sysmon-enhanced endpoint telemetry forwarded into Splunk SIEM for MITRE ATT&CK–mapped detections.

## 🎯 Objective
Build a realistic SOC-ready lab that demonstrates:
- Endpoint telemetry engineering (Sysmon)
- Centralized log ingestion (Splunk)
- Detection engineering and tuning
- MITRE ATT&CK mapping (Enterprise + OT-relevant thinking)

## 🏗️ Lab Architecture (High Level)
### Components
- **DC01** – Windows Server (Domain Controller)
- **Windows Workstation VM** – User endpoint
- **Sysmon** – High-fidelity endpoint telemetry
- **Splunk Enterprise** – SIEM for indexing/correlation
- **Splunk Universal Forwarder** – Log shipping

### Data Flow
1. Sysmon logs to Windows Event Log (Sysmon/Operational)
2. Splunk Universal Forwarder collects Sysmon + Security logs
3. Splunk indexes events
4. SPL detections generate alerts and dashboards

## 🔍 Telemetry: What Sysmon Captures
Focused Event IDs:
- **Event ID 1** – Process Creation (command line, parent process, hashes)
- **Event ID 3** – Network Connections (per process)
- **Event ID 13** – Registry Value Set (persistence)
- **Event ID 7** – DLL Load (injection visibility)
- **Event ID 2** – File creation time changes (timestomping)

## 🧠 Detection Use Cases (MITRE ATT&CK Mapped)

| Use Case | What It Detects | Sysmon Event | MITRE Technique |
|---|---|---:|---|
| Encoded PowerShell | Suspicious PowerShell execution patterns | 1 | T1059 |
| Suspicious Outbound Traffic | Potential C2 / beaconing | 3 | T1071 |
| Registry Persistence | Run key / persistence modifications | 13 | T1547 |
| Injection Indicators | Unusual DLL loads | 7 | T1055 |

## 🔎 Sample SPL Queries

### Encoded PowerShell
```spl
index=wineventlog EventCode=1
CommandLine="*EncodedCommand*"# ot-ics-soc-detection-lab
index=wineventlog EventCode=3
| stats count by Image, DestinationIp, DestinationPort
| sort - count


Commit it.

---

## 3) Fill each folder (step-by-step)

### A) `architecture/README.md`
Create this file and paste:

```markdown
# Architecture

## Network Segmentation
Document VLANs / subnets and why segmentation matters (reduce blast radius, easier troubleshooting).

## Data Flow
Sysmon → Windows Event Log → Splunk Forwarder → Splunk Index → Detections/Dashboards

## Diagrams to Add
- network_topology.png
- data_flow.png
