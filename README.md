# OT / ICS SOC Detection Lab

This project demonstrates a simulated industrial control system (ICS) security environment built using virtualization and open-source security tools.

The lab follows the Purdue Model architecture and includes enterprise IT systems, network segmentation, and industrial control systems.

## Lab Components

• VMware Workstation  
• Windows Server 2022 Domain Controller (DC01)  
• Windows 10 Workstation  
• pfSense Firewall  
• OpenPLC Industrial Controller  
• Kali Linux Attacker Machine  
• Splunk SIEM  

## Architecture

Enterprise Network
│
├── DC01 (Active Directory)
├── Windows 10 workstation
└── Splunk SIEM
        │
        │
     pfSense Firewall
        │
Industrial Network
│
└── OpenPLC (PLC)
        │
    Modbus devices

## Skills Demonstrated

• Active Directory administration  
• Network segmentation using pfSense  
• OT / ICS architecture based on the Purdue Model  
• Splunk SIEM log monitoring  
• Attack simulation using Kali Linux  
• Industrial protocol analysis (Modbus)

## Attack Simulations

1. Active Directory brute-force attack  
2. Lateral movement using compromised credentials  
3. PLC command injection via Modbus  

## Detection Engineering

Splunk queries are used to detect:

• abnormal login attempts  
• unusual Modbus commands  
• lateral movement across hosts
