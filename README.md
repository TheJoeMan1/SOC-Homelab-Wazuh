# SOC-Homelab-Wazuh
SOC Homelab simulating real-world attacks using Metasploit on a Windows victim, detected in real-time by Wazuh SIEM with custom MITRE ATT&amp;CK-mapped detection rules and automated active response.

# SOC Homelab — Wazuh SIEM + Metasploit Attack Simulation

## Overview
A fully functional Security Operations Center (SOC) homelab built from scratch to 
simulate real-world attacks and detect them using a SIEM.

## Architecture
| Machine | Role | IP |
|---|---|---|
| Kali Linux | Attacker | 192.168.56.1 |
| Wazuh OVA | SIEM | 192.168.56.10 |
| Windows 10 | Victim | 192.168.56.20 |

## Tools Used
- Wazuh SIEM v4.14
- Metasploit Framework
- msfvenom
- Sysmon
- VirtualBox Host-Only Network

## Attack Simulation
1. Generated reverse shell payload with msfvenom
2. Delivered payload via Python HTTP server
3. Opened Meterpreter session on Windows victim
4. Ran post-exploitation commands: whoami, systeminfo, net user, tasklist

## Detection — Custom Wazuh Rules
| Rule ID | Description | MITRE Technique |
|---|---|---|
| 100010 | Account enumeration via net.exe | T1087 |
| 100011 | System information gathering | T1082 |
| 100012 | Registry run key enumeration | T1547.001 |
| 100013 | Running process enumeration | T1057 |
| 100014 | Mimikatz / credential dumping | T1003 |
| 100015 | Suspicious PowerShell execution | T1059.001 |
| 100016 | Registry run key modification | T1547.001 |

## Active Response
Wazuh firewall-drop configured to automatically respond to detections.

## Screenshots
See /screenshots folder.

linkedin.com/in/thejoeman/
yossifmohamedabbas50@gmail.com
