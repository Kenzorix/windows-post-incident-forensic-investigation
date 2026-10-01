# Windows Post-Incident Forensic Investigation

## Case Overview

This project documents a simulated post-incident forensic investigation carried out on a Windows 10 victim machine.

The investigation focused on collecting and analysing disk and memory evidence, identifying persistence, reviewing user activity, and reconstructing the simulated attacker activity.

## Investigation Objectives

- Acquire and preserve forensic evidence
- Collect relevant Windows artifacts
- Analyse Windows Registry hives
- Review Windows Security events
- Analyse captured memory
- Investigate persistence mechanisms
- Identify and examine the simulated payload
- Reconstruct the activity observed on the system
- Map confirmed activity to MITRE ATT&CK
- Document findings, limitations, and recommendations

## Tools Used

- FTK Imager
- KAPE
- Registry Explorer
- Windows Event Viewer
- WinPmem
- Volatility 3
- Python
- MITRE ATT&CK

## Investigation Workflow

The investigation followed this general workflow:

1. Forensic acquisition and evidence preservation
2. Memory capture and hashing
3. Windows artifact collection with KAPE
4. Registry analysis
5. Windows Security log analysis
6. Memory analysis with Volatility 3
7. Timeline investigation
8. Persistence investigation
9. Attacker activity reconstruction
10. MITRE ATT&CK mapping
11. Findings and recommendations

## Key Finding

A Registry persistence entry was identified at:

`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

The value `DFIRCase001` was configured to execute:

`cmd.exe /c "C:\Users\Kenzorix\Downloads\payload.bat"`

The referenced batch file contained a command that created an execution marker in the user's temporary directory.

The marker file contained:

`DFIR-CASE-001-PAYLOAD-EXECUTED`

This provided an evidence chain linking the Registry persistence entry to the payload and its execution marker.

## Authentication Evidence

Windows Security logs were filtered for Event ID 4625.

The filter returned 41 events.

A selected event contained authentication information including:

- Target username: Kenzorix
- Logon Type: 2
- Logon Process: User32
- Authentication Package: Negotiate
- Process: C:\Windows\System32\svchost.exe
- IP Address: 127.0.0.1

These events were treated as authentication evidence and correlated with the other artifacts during the investigation.

## Memory and Timeline Analysis

A memory image was captured from the Windows 10 victim machine and analysed using Volatility 3.

Windows information was successfully identified from the memory image.

An automated timeline was also attempted with Volatility 3, but the expected timeline output was not produced in the lab environment. This was documented as a limitation and the available event logs and other artifacts were used for correlation.

## MITRE ATT&CK

The confirmed Registry persistence mechanism was mapped to:

**T1547.001 — Registry Run Keys / Startup Folder**

The mapping was based on the identified Registry Run value and the command used to launch the batch payload.

## Investigation Limitations

This investigation was performed in a controlled laboratory environment.

Some artifacts did not provide all of the expected information, including the NTUSER.dat artifact. The Volatility timeline generation also did not produce the expected output.

These limitations were documented rather than treating missing information as evidence.

## Repository Structure
- `acquisition/` — forensic acquisition and evidence preservation
- `artifact-collection/` — KAPE artifact collection
- `registry-analysis/` — Windows Registry investigation
- `event-log-analysis/` — Windows Security log analysis
- `memory-analysis/` — memory acquisition and Volatility analysis
- `timeline-analysis/` — timeline investigation
- `mitre-attack/` — ATT&CK mapping
- `attacker-reconstruction/` — reconstructed activity and persistence evidence
- `findings/` — investigation findings
- `recommendations/` — security and investigation recommendations

## Conclusion
The investigation established a clear evidence chain for the simulated persistence activity:

**Registry Run Key → DFIRCase001 → payload.bat → dfir_marker.txt**

The evidence from the Registry, Windows Security logs, memory, and collected artifacts was analysed together to reconstruct the activity observed on the victim machine.

This project demonstrates a practical DFIR workflow from evidence acquisition through analysis, correlation, and reporting.
