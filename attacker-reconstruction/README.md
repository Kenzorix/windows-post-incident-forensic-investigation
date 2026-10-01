# Attacker Reconstruction

## 1. Purpose

This stage was used to reconstruct the simulated attacker activity from the evidence collected from the Windows 10 victim machine.

The reconstruction focused on the persistence mechanism, the payload used, and evidence showing that the payload executed.

## 2. Registry Persistence

The Windows Registry was examined at:

`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

A Registry value named `DFIRCase001` was identified.

The value contained the following command:

`cmd.exe /c "C:\Users\Kenzorix\Downloads\payload.bat"`

This shows that the batch file was configured to execute through a Windows Registry autorun location.

## 3. Payload Identified

The referenced payload was located at:

`C:\Users\Kenzorix\Downloads\payload.bat`

The batch file contained:

`@echo off`

`echo DFIR-CASE-001-PAYLOAD-EXECUTED > "%TEMP%\dfir_marker.txt"`

The command writes a marker file to the user's temporary directory when the payload executes.

## 4. Execution Evidence

The file:

`%TEMP%\dfir_marker.txt`

was found on the victim system.

The contents of the file were:

`DFIR-CASE-001-PAYLOAD-EXECUTED`

This provided direct evidence that the payload's marker-writing action had occurred.

## 5. Reconstructed Activity

Based on the collected evidence, the simulated activity can be reconstructed as follows:

1. A batch payload was placed at `C:\Users\Kenzorix\Downloads\payload.bat`.
2. A Registry Run value named `DFIRCase001` was created under the current user's Run key.
3. The Run value was configured to execute the batch file using `cmd.exe`.
4. The batch file wrote an execution marker to `%TEMP%\dfir_marker.txt`.
5. The marker file was recovered and contained `DFIR-CASE-001-PAYLOAD-EXECUTED`.
6. The evidence was preserved and analysed as part of the forensic investigation.

## 6. MITRE ATT&CK Mapping

The Registry persistence mechanism corresponds to:

**T1547.001 — Registry Run Keys / Startup Folder**

The mapping is supported by the identified Run key and the `DFIRCase001` value that launches the batch payload.

## 7. Evidence

The following screenshots document the reconstructed activity:

- `REGISTRY_PERSISTENCE_DFIRCASE001.png` — Registry Run key and persistence value.
- `PAYLOAD_BAT_CONTENTS.png` — contents of the batch payload.
- `PAYLOAD_EXECUTION_MARKER.png` — execution marker created by the payload.

## 8. Limitations

The reconstruction describes activity performed in a controlled lab environment as part of the simulated incident.

The evidence establishes the Registry persistence configuration and the execution marker produced by the payload. It does not by itself establish that the same activity occurred through a real-world external attacker.

## 9. Conclusion

The collected evidence provides a clear chain between the Registry persistence entry, the batch payload, and the resulting execution marker.

This evidence was correlated with the other forensic artifacts collected during the investigation to support reconstruction of the simulated incident.
