
## Case ID
CASE-001
## Case Type

Post-Incident Windows Forensic Investigation

## Environment
- Victim: Windows 10 workstation
- Attacker: Ubuntu Linux VM
- Virtualization: VirtualBox
- Investigation performed in a controlled laboratory environment

## Incident Scenario

A Windows 10 workstation was used as the victim system in a simulated security incident.

The scenario involved execution of a suspicious update script. The activity resulted in the creation of an artifact and establishment of persistence through a Windows Registry Run Key.

The workstation was then preserved for forensic examination.

## Investigation Objectives

The investigation was performed to:

- Acquire and preserve forensic evidence
- Capture volatile memory
- Create a forensic disk image
- Verify evidence integrity using hashing
- Analyze Windows forensic artifacts
- Investigate suspicious execution activity
- Identify persistence mechanisms
- Reconstruct the sequence of attacker activity
- Map confirmed behaviors to MITRE ATT&CK

## Evidence Examined

- E01 forensic disk image
- Memory dump
- Windows Registry hives
- Prefetch artifacts
- ShellBags
- SAM hive
- SOFTWARE hive
- Windows Event Logs

## Confirmed Findings

The investigation identified:

1. PowerShell execution associated with the suspicious activity.
2. Creation of a suspicious artifact.
3. A Windows Registry Run Key configured for automatic execution.
4. Persistence through the Registry Run Key.

## Investigation Status

The available evidence was analyzed and the confirmed attacker behaviors were mapped to MITRE ATT&CK.

## Limitations

NTUSER.dat was not successfully acquired during the investigation and was therefore not treated as confirmed evidence.
