# Investigation Findings
## 1. Overview

This investigation examined a simulated security incident on a Windows 10 victim machine.

The investigation included forensic acquisition, memory capture, KAPE artifact collection, Registry analysis, Windows Security log analysis, memory analysis, timeline investigation, and MITRE ATT&CK mapping.

## 2. Registry Persistence

Registry analysis identified a persistence entry under:

`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

The Registry value was named:

`DFIRCase001`

The value executed:

`cmd.exe /c "C:\Users\Kenzorix\Downloads\payload.bat"`

This provided evidence of Registry-based persistence within the simulated incident.

## 3. Payload Analysis

The referenced file was:

`C:\Users\Kenzorix\Downloads\payload.bat`

The batch file contained a command that created an execution marker:

`DFIR-CASE-001-PAYLOAD-EXECUTED`

The marker was written to:

`%TEMP%\dfir_marker.txt`

## 4. Execution Evidence

The file `dfir_marker.txt` was found in the user's temporary directory.

The contents of the file were:

`DFIR-CASE-001-PAYLOAD-EXECUTED`

This provided supporting evidence that the payload's marker-writing action had executed on the victim system.

## 5. Authentication Activity

The Windows Security log was filtered for Event ID 4625.

The filter returned 41 events.

A selected event showed:

- Target username: Kenzorix
- Logon Type: 2
- Logon Process: User32
- Authentication Package: Negotiate
- Process: C:\Windows\System32\svchost.exe
- IP Address: 127.0.0.1

These events were treated as authentication evidence and were correlated with the other artifacts rather than being considered proof of compromise by themselves.

## 6. Memory Analysis

A memory image was captured from the Windows 10 victim machine and analysed using Volatility 3.

Windows information was successfully identified from the memory image.

Additional analysis was attempted to identify useful volatile evidence. Some analysis did not produce the expected output and this was documented as a limitation.

## 7. Timeline Analysis

Timeline generation was attempted using Volatility 3.

The automated timeline did not produce the expected output in the lab environment.

Relevant timestamps from the available forensic artifacts were therefore considered separately and correlated during the investigation.

## 8. Evidence Correlation

The investigation used multiple evidence sources, including:

- Forensic disk image
- KAPE-collected artifacts
- Windows Registry
- Windows Security logs
- Memory image
- Payload and execution marker
- Timeline-related evidence

Correlating these sources provided a stronger basis for reconstructing the simulated incident.

## 9. MITRE ATT&CK Mapping

The Registry persistence mechanism was mapped to:

**T1547.001 — Registry Run Keys / Startup Folder**

The mapping was supported by the identified Registry Run value and the command used to launch the batch payload.

## 10. Investigation Limitations

The investigation was performed in a controlled laboratory environment.

The NTUSER.dat artifact did not provide all of the expected information, and automated timeline generation with Volatility 3 did not produce the expected output.

These limitations were documented rather than treated as evidence.

## 11. Final Assessment

The investigation established a clear evidence chain for the simulated persistence activity:

**Registry Run Key → DFIRCase001 → payload.bat → dfir_marker.txt**

The Windows Security logs also provided authentication-related evidence through multiple Event ID 4625 events.

The findings were correlated across disk, Registry, memory, and Windows event evidence to reconstruct the simulated incident while keeping unsupported conclusions separate from documented evidence.
