
#  Task 7 — Detection Engineering & Purple Team Validation.

---

# Detection Engineering & Purple Team Validation - Building an Enterprise SOC Detection Pipeline

The final phase of Domain 2 shifted focus from offensive validation to defensive assurance. Every attack simulation performed throughout the project was mapped to enterprise telemetry, Windows Security Event Logs, network packet captures, and MITRE ATT&CK techniques to confirm that defensive controls generated actionable evidence for Security Operations Center (SOC) investigations.

Rather than asking whether an attack was possible, this assessment answered a more important operational question:

# Can the organization detect, investigate, and respond to the activity it experiences?

This project validates that enterprise security is strengthened not only through prevention, but through high-fidelity visibility, effective detection engineering, and continuous Purple Team collaboration.

Task 7 marked the transition from executing security assessments to validating whether an enterprise Security Operations Center (SOC) can detect, investigate, and respond to real-world attack activity. The objective was not simply to perform offensive techniques, but to confirm that defensive controls generated meaningful telemetry across the network, Active Directory, and Windows Security logs.

Throughout this phase, I simulated multiple stages of the cyber attack lifecycle within a controlled Active Directory environment. 

Activities included network reconnaissance using Nmap, LDAP enumeration, Active Directory relationship mapping with BloodHound, Kerberos ticket requests, Kerberoasting against a dedicated service account, WinRM-based remote administration, SMB SYSVOL enumeration, and packet-level validation using Wireshark. 

Every activity was correlated with Windows Security Event Logs in Splunk Enterprise and mapped to the MITRE ATT&CK framework to validate enterprise detection coverage.

From a Detection Engineering perspective, this exercise demonstrates how security teams transform offensive techniques into actionable detections. Rather than focusing solely on prevention, modern SOC operations prioritize visibility, alerting, investigation, and continuous improvement. 

By validating authentication events, service ticket requests, remote management sessions, file share access, and reconnaissance activities, I confirmed that defensive telemetry accurately reflected each stage of the simulated attack chain.

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

# The ability to validate telemetry across:

* Active Directory
* Windows Security Logs
* Network traffic
* Authentication events
* Remote administration protocols

is a core requirement across modern enterprise environments and cloud-connected infrastructures.

---

Throughout Domain 2, an enterprise Active Directory environment was constructed and used to simulate realistic adversary behavior across the Cyber Kill Chain. Each action was intentionally performed to generate authentic security telemetry that could be validated in Splunk Enterprise and correlated with packet-level evidence captured in Wireshark.

# The assessment covered the complete detection lifecycle:

Network reconnaissance
Active Directory enumeration
LDAP discovery
Kerberos authentication
Kerberoasting
Remote administration through WinRM
SMB administrative share access
RPC communication
Packet capture validation
Windows Security Event correlation
MITRE ATT&CK mapping
Purple Team detection validation
Enterprise Objectives

# This project was designed to answer key enterprise security questions:

**Can reconnaissance activity be identified?**
**Are authentication events fully logged?**
**Can Kerberos abuse be detected?**
**Does remote administration generate sufficient telemetry?**
**Does packet-level evidence align with Windows Event Logs?**
**Can SOC analysts correlate attacker activity across multiple telemetry sources?**

# Technologies Used

- Windows Server 2019
- Active Directory Domain Services
- Kali Linux
- Splunk Enterprise
- Sysmon
- Wireshark
- Nmap
- BloodHound
- BloodHound.py
- Impacket
- John the Ripper
- Evil-WinRM
- SMBClient
- RPCClient
- PowerShell

# Detection Engineering Validation

Reconnaissance Detection
Enterprise reconnaissance was simulated using Nmap service and operating system discovery scans.

# Validated detections included:

- Network Service Discovery
- TCP service enumeration
- Port scanning activity
- Host fingerprinting

# MITRE ATT&CK

T1046 — Network Service Discovery
Active Directory Enumeration

Directory reconnaissance was performed using BloodHound and BloodHound.py to enumerate users, groups, computers, organizational units, and attack paths.

# Validated detections included:

LDAP queries
Account discovery
Domain object enumeration
Directory service access

# MITRE ATT&CK

T1087 — Account Discovery
T1482 — Domain Trust Discovery
T1018 — Remote System Discovery
Kerberos Authentication Validation

# Enterprise authentication activity generated:

Ticket Granting Ticket (TGT) requests
Service Ticket (TGS) requests
Successful logons
Administrative logons

# Validated Windows Security Events:

Event ID 4624
Event ID 4648
Event ID 4672
Event ID 4768
Event ID 4769
Event ID 4776

# MITRE ATT&CK

T1558
T1078

# Kerberoasting Detection

A service account was configured with a Service Principal Name (SPN), after which Impacket was used to request a Kerberos Service Ticket.

The extracted Kerberos ticket was subsequently audited offline using John the Ripper to validate password auditing workflows and demonstrate the risk associated with weak service account credentials.

# Detection validation confirmed:

Kerberos Service Ticket requests
Service account visibility
Offline password auditing workflow
Detection opportunities for Kerberoasting activity

# MITRE ATT&CK

T1558.003 — Kerberoasting
Lateral Movement Validation

Enterprise administrative protocols were validated using native Windows management technologies.

# Protocols validated:

WinRM
SMB
RPC
SYSVOL
NETLOGON

# MITRE ATT&CK

T1021.006 — Windows Remote Management
T1021.002 — SMB/Windows Admin Shares
Splunk Detection Library

**The following Windows Security Events were successfully validated during the assessment:**

Event ID	Detection Purpose

4624	Successful Logon
4625	Failed Logon
4648	Explicit Credentials
4672	Privileged Logon
4768	Kerberos Ticket Granting Ticket
4769	Kerberos Service Ticket
4776	NTLM Authentication
4662	Directory Service Access
5156	Windows Filtering Platform Connection
5158	Port Binding Activity
4688	Process Creation
4627	Group Membership Enumeration

These detections demonstrated that enterprise telemetry accurately reflected every stage of the simulated attack lifecycle.

# Wireshark Validation

Packet captures confirmed visibility into enterprise network protocols, including:

Kerberos (AS-REQ, AS-REP, TGS-REQ, TGS-REP)
LDAP
SMB2
DCERPC
WinRM (HTTP/5985)
DNS
TCP session establishment

# The captured traffic was correlated directly with Windows Security Events to validate end-to-end detection capabilities.

MITRE ATT&CK Mapping
Activity	Technique
Network Reconnaissance	T1046
Account Discovery	T1087
Remote System Discovery	T1018
Domain Trust Discovery	T1482
Kerberos Authentication	T1558
Kerberoasting	T1558.003
Valid Accounts	T1078
WinRM	T1021.006
SMB Shares	T1021.002
Purple Team Validation

# This assessment demonstrated the complete Purple Team lifecycle by validating:

Offensive simulation
Telemetry generation
Packet capture
Windows Event logging
Splunk ingestion
Detection engineering
ATT&CK mapping
SOC investigation readiness

Every offensive action was intentionally correlated with defensive evidence, enabling repeatable validation of enterprise detection capabilities.

# Skills Demonstrated

Detection Engineering
Purple Team Operations
Threat Detection
SIEM Engineering
Windows Event Analysis
Active Directory Security
Kerberos Security
Enterprise Authentication
Packet Analysis
Network Forensics
Splunk Enterprise
Wireshark
MITRE ATT&CK
Threat Hunting
Security Monitoring
SOC Operations

# Key Outcomes

**Simulated a complete enterprise attack chain from reconnaissance through lateral movement.**
**Validated more than a dozen Windows Security Event IDs in Splunk Enterprise.**
**Correlated host-based telemetry with packet captures collected in Wireshark.**
**Demonstrated Kerberoasting detection and offline password auditing using enterprise security tooling.**
**Mapped offensive activity to the MITRE ATT&CK framework to strengthen detection coverage.**
**Produced repeatable detection engineering artefacts suitable for Purple Team exercises and SOC investigations.**

# Conclusion

Detection engineering is the discipline that transforms raw telemetry into operational awareness. This project demonstrated how enterprise attack simulations can be systematically correlated with Windows Event Logs, network traffic, and SIEM analytics to produce actionable detections rather than isolated alerts.

By validating reconnaissance, authentication, Kerberos abuse, lateral movement, and administrative activity against real telemetry, this assessment illustrates the collaborative relationship between offensive security and defensive operations. The result is a repeatable Purple Team methodology that helps organizations continuously improve detection coverage, investigation workflows, and incident response readiness.

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

# Author's Summary

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
* ✅ **QUESTION 1:** Who are the identities? (BloodHound attack paths)
* ✅ **QUESTION 2:** What identity risks exist? (Identity exposure analysis)
* ✅ **QUESTION 3:** What infrastructure is exposed? (Enterprise enumeration)
* ✅ **QUESTION 4:** What services and configurations are vulnerable? (Vulnerability assessment)
* ✅ **QUESTION 5:** Can identity be abused? (Kerberoasting)
* ✅ **QUESTION 6:** Can an attacker move laterally? (WinRM/SMB validation)
* ✅ **QUESTION 7:** Can the SOC detect it? (Detection Engineering & Purple Team validation)

This forms a coherent, end-to-end project that mirrors the workflow of an enterprise SOC, Detection Engineering, and 
Purple Team engagement, with evidence collected at the network, endpoint, identity, and SIEM layers. 
It is a strong portfolio artifact for roles such as SOC Analyst, Detection Engineer, Purple Team Operator, Security Engineer, 
Incident Responder.

Enterprise Active Directory Attack Simulation, Detection Engineering, and Purple Team Validation successfully completed with 
end-to-end visibility across network telemetry, authentication events, packet captures, SIEM detections, and MITRE ATT&CK 
mapping.


# Author

BASSEY SOLOMON HENRY

Cybersecurity Engineer | SOC Analyst | Detection Engineer | Purple Team | Active Directory Security

Passionate about building enterprise-scale security labs that simulate real-world adversary techniques while strengthening detection engineering, threat hunting, and defensive operations.

# Connect With Me

💼 LinkedIn: https://www.linkedin.com/in/bassey-solomon-henry/

🌐 GitHub: https://github.com/solomonhenry-afk/Bassey-Solomon-Henry📧 Email: solomon_henry111@outlook.com
Tech Stack & GitHub Analytics
<p align="center"> <img src="https://skillicons.dev/icons?i=linux,bash,powershell,python,git,github,vscode"/> </p> <p align="center"> <img src="https://github-readme-stats.vercel.app/api?username=solomonhenry-afk&show_icons=true&theme=tokyonight"/> <img src="https://github-readme-streak-stats.herokuapp.com/?user=solomonhenry-afk&theme=tokyonight"/> </p> <p align="center"> <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=solomonhenry-afk&layout=compact&theme=tokyonight"/> </p>

"Security is not measured by preventing every attack. It is measured by understanding systems deeply enough to detect, investigate, and continuously improve against evolving threats."

— Solomon Henry
