
#  Task 7 — Detection Engineering & Purple Team Validation.

---

# Detection Engineering & Purple Team Validation — Building an Enterprise SOC Detection Pipeline

Task 7 marked the transition from executing security assessments to validating whether an enterprise Security Operations Center (SOC) can detect, investigate, and respond to real-world attack activity. The objective was not simply to perform offensive techniques, but to confirm that defensive controls generated meaningful telemetry across the network, Active Directory, and Windows Security logs.

Throughout this phase, I simulated multiple stages of the cyber attack lifecycle within a controlled Active Directory environment. Activities included network reconnaissance using Nmap, LDAP enumeration, Active Directory relationship mapping with BloodHound, Kerberos ticket requests, Kerberoasting against a dedicated service account, WinRM-based remote administration, SMB SYSVOL enumeration, and packet-level validation using Wireshark. Every activity was correlated with Windows Security Event Logs in Splunk Enterprise and mapped to the MITRE ATT&CK framework to validate enterprise detection coverage.

From a Detection Engineering perspective, this exercise demonstrates how security teams transform offensive techniques into actionable detections. Rather than focusing solely on prevention, modern SOC operations prioritize visibility, alerting, investigation, and continuous improvement. By validating authentication events, service ticket requests, remote management sessions, file share access, and reconnaissance activities, I confirmed that defensive telemetry accurately reflected each stage of the simulated attack chain.

The project also reinforced the importance of Purple Team collaboration, where offensive security activities directly improve defensive monitoring. Each validated event contributes to stronger detection content, more effective investigation playbooks, and measurable improvements in enterprise security maturity.

---

## Enterprise Objective

Develop and validate enterprise detection capabilities for:

* Network reconnaissance
* Service discovery
* Active Directory enumeration
* LDAP queries
* Kerberos authentication
* Kerberoasting attacks
* SMB share enumeration
* WinRM remote administration
* Packet-level traffic validation
* SIEM detection engineering
* MITRE ATT&CK coverage validation

---

## Business Impact

Enterprise organizations increasingly assume that attackers will gain an initial foothold. The primary objective therefore becomes rapid detection, investigation, and containment rather than relying solely on preventive controls.

This project demonstrates practical experience in validating whether enterprise logging infrastructure provides sufficient visibility into identity attacks, reconnaissance, credential abuse, and lateral movement. These capabilities directly support Security Operations Centers (SOC), Incident Response teams, Threat Hunting programs, Purple Team engagements, and Detection Engineering initiatives.

---

## Why This Matters

Detection engineering transforms raw security telemetry into meaningful alerts that enable analysts to identify malicious behavior before significant business impact occurs.

The ability to validate telemetry across:

* Active Directory
* Windows Security Logs
* Network traffic
* Authentication events
* Remote administration protocols

is a core requirement across modern enterprise environments and cloud-connected infrastructures.

---

## Enterprise Skills Demonstrated

* Detection Engineering
* Purple Team Operations
* SOC Validation
* Threat Hunting
* Active Directory Security
* Identity Attack Detection
* Windows Event Log Analysis
* Splunk Enterprise SIEM
* Wireshark Network Analysis
* MITRE ATT&CK Mapping
* Authentication Monitoring
* Kerberos Security
* SMB Security Monitoring
* WinRM Security Validation

---

# Purple Team Validation Summary

The complete attack lifecycle was successfully executed and validated.

Validated attack phases included:

- Network reconnaissance
- Service discovery
- LDAP enumeration
- BloodHound Active Directory collection
- Kerberos authentication
- Kerberoasting simulation
- Service ticket requests
- WinRM remote management
- SMB SYSVOL enumeration
- Packet capture validation
- Windows Security Event validation
- Splunk Enterprise correlation
- MITRE ATT&CK mapping

---

# Detection Engineering Validation

The following enterprise detections were successfully validated.

| Detection Area              | Status  |
| ----------------------------|---------|
| Network Reconnaissance      | ✅      |
| LDAP Enumeration            | ✅      |
| Active Directory Discovery  | ✅      |
| Kerberos Authentication     | ✅      |
| Kerberoasting Detection     | ✅      |
| WinRM Lateral Movement      | ✅      |
| SMB Share Enumeration       | ✅      |
| Wireshark Packet Validation | ✅      |
| Splunk Event Correlation    | ✅      |
| MITRE ATT&CK Mapping        | ✅      |

---

# Enterprise Tools Used

**Reconnaissance**

* Nmap

**Directory Enumeration**

* BloodHound
* BloodHound.py
* Impacket GetADUsers

**Credential Access**

* Impacket GetUserSPNs
* John the Ripper

**Remote Administration**

* Evil-WinRM

**File Share Enumeration**

* smbclient
* rpcclient

**Network Visibility**

* Wireshark

**Security Monitoring**

* Splunk Enterprise

**Threat Framework**

* MITRE ATT&CK

---

# Detection Engineering Deliverables

This task produced a complete enterprise detection package including:

* Detection Rule Validation
* Purple Team Validation Report
* Windows Security Event Analysis
* Active Directory Attack Mapping
* Authentication Baseline
* Kerberos Attack Detection
* Splunk Detection Library
* Wireshark Network Evidence
* MITRE ATT&CK Mapping Matrix
* Executive Security Summary

---

# Executive Summary

Task 7 demonstrates an end-to-end enterprise detection engineering workflow, beginning with reconnaissance and progressing through Active Directory enumeration, authentication, credential access, and lateral movement. Every stage of the simulated attack chain was validated using Windows Security Event Logs, packet captures, and Splunk Enterprise searches, confirming that defensive controls produced actionable telemetry aligned with the MITRE ATT&CK framework.

This exercise reflects the collaborative nature of Purple Team operations, where offensive techniques are used to measure and improve defensive visibility. By correlating network activity, authentication events, and endpoint logs, the project showcases the practical skills required to develop detection content, investigate security events, and strengthen enterprise monitoring capabilities.

---

# HR / Recruiter Summary

This portfolio demonstrates practical experience with:

* Enterprise Active Directory Security
* Detection Engineering
* Purple Team Operations
* SOC Monitoring
* Threat Hunting
* Windows Security Logging
* Splunk Enterprise
* Wireshark Analysis
* Kerberos Security
* Identity Attack Detection
* MITRE ATT&CK
* Incident Investigation
* Authentication Monitoring
* Enterprise Security Validation

---

## Final Project Status

Across **Domain 2**, I have now built and documented a complete enterprise identity attack and detection lifecycle:

* ✅ **Task 1:** Active Directory Deployment & Enterprise Identity Infrastructure
* ✅ **Task 2:** Windows Logging, Sysmon & Splunk Integration
* ✅ **Task 3:** Network Traffic Baseline & Authentication Visibility
* ✅ **Task 4:** Vulnerability Assessment & Service Exposure Analysis
* ✅ **Task 5:** Enterprise Identity Attack Path Validation (Kerberoasting)
* ✅ **Task 6:** Lateral Movement Validation (WinRM & SMB)
* ✅ **Task 7:** Detection Engineering & Purple Team Validation

This forms a coherent, end-to-end project that mirrors the workflow of an enterprise SOC, Detection Engineering, and 
Purple Team engagement, with evidence collected at the network, endpoint, identity, and SIEM layers. 
It is a strong portfolio artifact for roles such as SOC Analyst, Detection Engineer, Purple Team Operator, Security Engineer, 
Incident Responder.

Status: ✅ Completed

Enterprise Active Directory Attack Simulation, Detection Engineering, and Purple Team Validation successfully completed with 
end-to-end visibility across network telemetry, authentication events, packet captures, SIEM detections, and MITRE ATT&CK 
mapping.

# Author: Bassey Solomon Henry
