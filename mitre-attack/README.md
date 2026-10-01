# MITRE ATT&CK Mapping

## 1. Purpose

MITRE ATT&CK was used to map the observed activity to documented adversary techniques.

The mapping was based on the forensic evidence collected during the investigation.

Only techniques supported by the available evidence were included.

## 2. Persistence

### T1547.001 — Registry Run Keys / Startup Folder

The investigation included examination of Windows Registry locations associated with startup and persistence.

This technique was considered because Registry Run Keys can be used to automatically execute a program when a user logs in.

The registry evidence was reviewed together with the other collected artifacts to determine whether the persistence activity was relevant to the incident.

## 3. Valid Accounts / Authentication Activity

### Event ID 4625

The Windows Security log contained multiple failed logon events identified as Event ID 4625.

These events were used as supporting authentication evidence during the investigation.

Event ID 4625 itself is a Windows event identifier rather than a MITRE ATT&CK technique, so it was not treated as a technique on its own.

The authentication evidence was instead used to provide context for the overall investigation.

## 4. Evidence Used for Mapping

The MITRE ATT&CK mapping was based on evidence from:

- Windows Registry analysis
- Windows Security Event Logs
- KAPE-collected artifacts
- Memory analysis
- Timeline investigation

## 5. Limitations

MITRE ATT&CK techniques were not assigned solely because an artifact was present.

A technique was considered only where the available evidence could reasonably support the behavior being mapped.

Further evidence would be required to confidently map additional techniques.

## 6. Conclusion

MITRE ATT&CK provided a standardized way to describe and organize the behaviors observed during the forensic investigation.

The mapping was kept evidence-based and was correlated with the findings from the other investigation stages.
