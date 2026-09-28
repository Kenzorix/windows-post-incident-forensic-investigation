# Windows Post-Incident Forensic Investigation

## Overview

A hands-on Digital Forensics and Incident Response (DFIR) investigation of a Windows 10 workstation following a simulated security incident.

The investigation focuses on forensic acquisition, evidence preservation, disk and memory analysis, Windows artifact analysis, persistence identification, attack reconstruction, and MITRE ATT&CK mapping.

---

## Investigation Scenario

A Windows 10 workstation was suspected of compromise after a suspicious update script was executed.

The simulated activity involved:

- Execution of a suspicious PowerShell script
- Creation of a forensic artifact
- Establishment of persistence through a Windows Registry Run Key
- Subsequent forensic acquisition and analysis of the affected workstation

The objective was to determine what happened, identify relevant forensic evidence, establish the attack sequence, and map confirmed attacker behaviors to MITRE ATT&CK.

---

## Investigation Objectives

- Preserve and acquire forensic evidence
- Create and verify a forensic disk image
- Capture volatile memory
- Analyze Windows forensic artifacts
- Investigate suspicious process execution
- Identify persistence mechanisms
- Reconstruct the attack timeline
- Identify relevant indicators of compromise
- Map confirmed behaviors to MITRE ATT&CK
- Document findings and limitations

---

## Investigation Environment

| Component | Details |
|---|---|
| Victim System | Windows 10 |
| Attacker System | Ubuntu Linux |
| Virtualization | VirtualBox |
| Disk Acquisition | FTK Imager |
| Disk Image | E01 |
| Memory Analysis | Volatility 3 |
| Registry Analysis | Registry Explorer |
| Artifact Collection | KAPE |
| Event Analysis | Windows Event Logs |
| Network Analysis | Wireshark |
| ATT&CK Mapping | MITRE ATT&CK |

---

## Evidence

The investigation involved the following evidence sources:

- Forensic disk image (E01)
- Volatile memory capture
- Windows Registry hives
- Prefetch artifacts
- ShellBags
- Windows account information from the SAM hive
- Windows system/software configuration from the SOFTWARE hive
- Execution and persistence artifacts

> Raw forensic images and memory dumps are not included in this repository because of their size and the potential presence of sensitive data.

---

## Investigation Methodology

The investigation followed a forensic workflow:

```text
Incident Scenario
       ↓
Evidence Preservation
       ↓
Disk Acquisition
       ↓
Memory Acquisition
       ↓
Hash Verification
       ↓
Artifact Collection
       ↓
Disk Analysis
       ↓
Memory Analysis
       ↓
Registry Analysis
       ↓
Execution & Persistence Analysis
       ↓
Timeline Reconstruction
       ↓
MITRE ATT&CK Mapping
       ↓
Final Findings


---

Key Findings

The investigation identified evidence of:

1. PowerShell script execution.


2. Creation of a suspicious artifact during script execution.


3. Registry Run Key persistence.


4. Automatic execution of the suspicious launcher at user logon.


5. Evidence of suspicious process execution within the acquired forensic evidence.

---

MITRE ATT&CK Mapping

Evidence	Attacker Behavior	Technique	Tactic

PowerShell executed the suspicious script	PowerShell execution	T1059.001 – PowerShell	Execution
Registry Run Key configured to launch the suspicious program	Automatic execution at logon	T1547.001 – Registry Run Keys / Startup Folder	Persistence


Mapping Method

The mapping was performed using:

Evidence
   ↓
What happened?
   ↓
Why did it happen?
   ↓
How was it performed?
   ↓
MITRE ATT&CK Technique

Only behaviors supported by the available evidence were mapped.


---

Forensic Artifacts

Prefetch

Used to investigate evidence of program execution on the Windows system.

SAM

Used as a source of Windows local-account information.

SOFTWARE Hive

Used to investigate Windows system configuration and installed software.

ShellBags

Used to investigate evidence of user interaction with folders and directories.

Memory

Used to investigate processes and activity present in memory at the time of acquisition.

NTUSER.dat

NTUSER.dat was not successfully acquired during this investigation and was therefore not treated as confirmed evidence.


---

Attack Reconstruction

The confirmed attack sequence can be summarized as:

Suspicious Script
       ↓
PowerShell Execution
       ↓
Artifact Creation
       ↓
Registry Run Key Modification
       ↓
Automatic Execution at Logon
       ↓
Persistence


---

Evidence Integrity

Forensic evidence was acquired and handled using forensic tools and hashing procedures.

Hash values were used to support evidence integrity and verify acquired evidence.


---

Limitations

NTUSER.dat was not successfully acquired.

Analysis was limited to artifacts successfully recovered during the investigation.

The investigation was conducted in a controlled virtualized laboratory environment.

Findings are based on the available forensic evidence and should not be extended beyond what the evidence supports.



---

Tools Used

FTK Imager

KAPE

Registry Explorer

Volatility 3

Windows Event Viewer

Wireshark

MITRE ATT&CK

VirtualBox



---

Learning Outcomes

This investigation provided practical experience with:

Digital evidence acquisition

Forensic imaging

Evidence hashing

Windows artifact analysis

Memory forensics

Registry analysis

Persistence investigation

Attack reconstruction

MITRE ATT&CK mapping

DFIR documentation

---

Disclaimer

This project was conducted in a controlled laboratory environment for educational and portfolio purposes.

No real-world victim systems were investigated.
