# Detection: Unauthorized Modbus Write Command

## Purpose

Detect unauthorized write commands sent to industrial devices using the Modbus protocol.

## Risk

Unauthorized Modbus write commands may indicate an attempt to manipulate industrial control systems.

## Data Source

Network telemetry from OT devices or protocol monitoring tools.

## Example Detection Logic

Alert when Modbus function codes related to write operations are observed:

- Function Code 5 – Write Single Coil
- Function Code 6 – Write Single Register
- Function Code 15 – Write Multiple Coils
- Function Code 16 – Write Multiple Registers

## MITRE ATT&CK ICS

T0855 – Unauthorized Command Message

## Investigation Steps

1. Identify source IP sending Modbus commands
2. Identify destination PLC or industrial device
3. Confirm if activity was authorized engineering activity
4. Investigate surrounding network traffic

## Tuning Notes

Filter known engineering workstations, maintenance windows, and approved change activity.
