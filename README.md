# Windows Firewall Hardening & SOC Log Analysis Lab

## Overview
A hands-on cybersecurity lab demonstrating Windows Firewall hardening, Nmap-based port scanning, and firewall log analysis using Kali Linux and Windows 11.

## Objectives
- Reduce unnecessary network exposure.
- Apply and verify Windows Firewall rules.
- Compare network scan results before and after hardening.
- Analyze dropped traffic and identify possible port-scanning activity.
- Document findings from a beginner SOC analyst perspective.

## Lab Environment
- Windows 11 — target system and firewall log analysis
- Kali Linux — authorized scanning host
- Nmap — port scanning and verification
- PowerShell — firewall administration and log filtering

## Results
The recorded scan comparison showed:
- Before hardening: 4 open ports (135, 139, 445, 8080).
- After hardening: 1 open port (8080).
- Ports 135, 139, and 445 were no longer reported as open.
- The intended service on port 8080 returned HTTP 200 OK.
- Firewall logs contained dropped TCP connection attempts from the Kali test host.

## SOC Log Analysis
The Windows Firewall log showed repeated DROP TCP entries from the test host to destination ports 135, 139, and 445. Repeated SYN packets targeting multiple ports are consistent with network reconnaissance.

The observed log excerpt did not include every port probed by the scanner. This is a visibility limitation of the collected evidence, not proof that every probe was logged.

## Evidence
The `evidence/` directory contains selected firewall configuration and log-analysis outputs.

## Safety and Privacy
This lab was conducted in a controlled environment on systems under the operator's authorization. Before publishing evidence, remove personal information, MAC addresses, unrelated device IP addresses, and other sensitive details.

## Conclusion
This project demonstrates practical experience with firewall hardening, attack-surface reduction, Nmap verification, PowerShell log filtering, and basic SOC investigation.

## Disclaimer
For educational and authorized defensive security testing only.
