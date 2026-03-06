# SOC Detection Lab – Splunk + Sysmon + Active Directory

Author: Jerald L. Burgess

This project simulates a **Security Operations Center (SOC) detection environment** designed to demonstrate enterprise security monitoring, detection engineering, and incident investigation workflows.

The lab replicates real-world security monitoring scenarios used in enterprise environments and industrial networks.

---

## Technologies Used

• Splunk Enterprise SIEM  
• Windows Event Logs  
• Sysmon Endpoint Telemetry  
• Active Directory Domain Environment  
• Windows 10 Endpoint  
• Splunk Universal Forwarder  

---

## Lab Architecture

Environment components:

| System | Role |
|------|------|
| Splunk Server | Security Information and Event Management |
| DC01 | Active Directory Domain Controller |
| WIN10-CL1 | Windows Endpoint Workstation |
| Sysmon | Endpoint Telemetry Collection |
| Splunk Universal Forwarder | Log Forwarding Agent |

### Data Flow

---

## Detection Engineering Scenarios

This lab demonstrates detection engineering use cases including:

• Privileged logon detection  
• Suspicious PowerShell execution  
• Lateral movement detection  
• Credential dumping indicators  
• Suspicious process activity  

---

## Incident Investigations

Each detection scenario includes a complete SOC investigation.

Example:

### IR-001 – Privileged Logon Investigation

Investigation workflow:

1. Detect privileged logon event
2. Correlate authentication logs
3. Review process execution
4. Investigate network connections
5. Document findings

Evidence includes:

• Splunk search queries  
• timeline reconstruction  
• screenshots of events  

---

## MITRE ATT&CK Mapping

| Detection | ATT&CK Technique |
|---|---|
| Privileged Logon | T1078 Valid Accounts |
| Suspicious PowerShell | T1059 Command Execution |
| Lateral Movement (RDP) | T1021 Remote Services |
| Credential Dumping | T1003 Credential Dumping |

---

## Future Enhancements

Planned improvements:

• OT device monitoring (Modbus)  
• firewall log integration  
• additional attack simulations  
• automated detection alerts  

---

## Skills Demonstrated

• SIEM deployment and log ingestion  
• Windows log analysis  
• Endpoint telemetry monitoring  
• Detection engineering  
• SOC incident investigation  
• Security documentation
