```markdown
# DetectionLab — Blue Team Detection & Investigation

## Overview

This repository documents a hands-on **DetectionLab** environment built to simulate a small Windows enterprise network and practice defensive security operations from a **SOC perspective**.

The objective of this lab was not simply to deploy the environment, but to use it as a practical training platform for:

- Attack simulation
- Security monitoring
- Log analysis
- Network analysis
- Detection engineering
- Incident investigation

The work documented here focuses on understanding **how attacker activity appears across different telemetry sources** and how a defender can correlate those artifacts to investigate suspicious behavior.

---

## Lab Environment

The lab simulates a Windows Active Directory environment with multiple systems generating security telemetry.

**Key components used during the lab include:**

- Active Directory / Domain Controller
- Windows workstation
- Windows Event Forwarding (WEF)
- Splunk
- Sysmon
- Wireshark
- Vagrant
- VirtualBox

The environment was used to generate and investigate realistic attack activity rather than relying exclusively on pre-generated examples.

---

## Areas of Practice

### Active Directory Security

- Active Directory enumeration
- Domain and user investigation
- Kerberos authentication analysis
- NTLM authentication analysis
- Windows security event analysis
- Account creation and modification monitoring
- Logon investigation
- Privilege-related activity
- Domain Controller telemetry

### Attack Simulation

The lab was used to simulate and investigate several common attack techniques, including:

- Network reconnaissance
- Nmap scanning
- Kerberos enumeration
- Credential dumping
- NTDS.DIT / Active Directory credential extraction
- DCSync
- Pass-the-Hash
- Persistence
- Lateral Movement

### Detection & Monitoring

- Splunk-based security monitoring
- Windows Event Log analysis
- Sysmon telemetry
- Event correlation
- Source IP investigation
- Account activity investigation
- Suspicious authentication analysis
- Detection-oriented SPL queries
- MITRE ATT&CK technique mapping

### Network Analysis

- Wireshark packet analysis
- SMB traffic investigation
- Kerberos traffic analysis
- Network conversations
- TCP/UDP analysis
- Network reconnaissance detection
- Authentication traffic investigation
- Traffic correlation with endpoint events

### Detection Engineering

A major objective of the lab was to move beyond simply observing attacks and understand how they can be detected.

**Examples of investigated telemetry:**

| Event / Telemetry | Investigation Focus                   |
| ----------------- | ------------------------------------- |
| Event ID 4624     | Successful logon investigation        |
| Event ID 4662     | Directory Service object access       |
| Event ID 4720     | User account creation                 |
| Event ID 4722     | User account enabled                  |
| Event ID 4724     | Password reset attempt                |
| Event ID 4725     | User account disabled                 |
| Event ID 4740     | Account lockout                       |
| Event ID 4768     | Kerberos authentication / TGT request |
| Sysmon            | Endpoint process and system activity  |
| Wireshark         | Network-level investigation           |
| Splunk            | Log search, filtering and correlation |

The emphasis was on understanding **what the event means**, **why it matters**, **what additional telemetry is required**, and **how multiple events can be correlated** into an investigation.

---

## Investigation Examples

The screenshots and report included in this repository document practical investigations such as:

- Successful Windows logon investigation using Event ID 4624
- Source IP analysis
- Investigation of authentication originating from a workstation
- Nmap reconnaissance activity
- Anonymous authentication activity
- Kerberos traffic analysis
- SMB communication analysis
- Active Directory object access
- User account creation
- Account-related security events
- Wireshark endpoint and conversation analysis
- Network traffic visualization
- Correlation of endpoint and network telemetry

---

## Repository Structure

```text
DetectionLab/
│
├── README.md
├── DetectionLab-Report.pdf
│
└── Screenshots/
    ├── 01-Splunk-4624-Source-IP-Analysis.png
    ├── 02-Wireshark-SMB-Analysis.png
    ├── 03-Wireshark-Kerberos-Analysis.png
    ├── 04-Splunk-4624-Logon-Analysis.png
    ├── 05-Splunk-4662-Directory-Service-Analysis.png
    ├── 06-Splunk-4720-User-Creation-Analysis.png
    ├── 07-Splunk-4624-Logon-Overview.png
    ├── 08-Splunk-4768-Kerberos-Analysis.png
    ├── 09-Splunk-4624-Workstation-Analysis.png
    ├── 10-Windows-Event-Analysis.png
    ├── 11-Wireshark-Network-Traffic-Analysis.png
    └── 12-Wireshark-TCP-SMB-Analysis.png
```

---

## Skills Demonstrated

- Security Operations Center (SOC) investigation
- Windows Event Log analysis
- Active Directory security monitoring
- Authentication analysis
- Kerberos investigation
- NTLM investigation
- Splunk SPL
- Sysmon analysis
- Network traffic analysis
- Wireshark
- SMB analysis
- Network reconnaissance detection
- Attack-chain investigation
- IOC identification
- Event correlation
- Detection engineering
- MITRE ATT&CK mapping
- Incident investigation

---

## Objective

This project represents a hands-on **Blue Team training environment** focused on developing practical SOC and detection engineering skills.

Rather than treating individual attacks as isolated exercises, the lab was used to understand the relationship between:

```text
Attack Activity
      ↓
Endpoint Telemetry
      ↓
Windows Event Logs / Sysmon
      ↓
Network Telemetry
      ↓
Splunk
      ↓
Correlation & Investigation
      ↓
Detection
```

The accompanying **PDF** contains the detailed technical documentation and investigation results, while the `Screenshots/` directory provides supporting evidence from the lab environment.
