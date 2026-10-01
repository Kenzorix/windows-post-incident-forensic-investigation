
# Registry Analysis

## 1. Purpose

After collecting the Windows artifacts with KAPE, I moved on to the Windows Registry analysis.

The goal was to examine the collected registry hives for evidence of user activity, system configuration, and possible persistence mechanisms on the Windows 10 victim machine.

## 2. Tools Used

- Registry Explorer
- KAPE

## 3. Registry Hives Examined

The following registry artifacts were collected during the KAPE collection:

- NTUSER.dat
- SAM
- SOFTWARE
- Other supporting registry artifacts

These hives were examined using Registry Explorer to identify information relevant to the investigation.

## 4. Analysis Process

I loaded the collected registry hives into Registry Explorer and reviewed the available keys and values.

The analysis focused mainly on registry locations that could provide evidence of user activity, system configuration, and persistence.

The registry evidence was also compared with other artifacts collected during the investigation to avoid relying on a single source of evidence.

## 5. Persistence Investigation

As part of the investigation, I reviewed registry locations commonly associated with Windows startup and persistence mechanisms.

The purpose was to determine whether a program or script had been configured to execute automatically when the system started or when a user logged in.

Any suspicious registry entry identified during the analysis would be correlated with other forensic evidence before being considered part of the incident.

## 6. User Activity

The NTUSER.dat hive was examined as part of the user activity investigation.

However, the available NTUSER.dat artifact did not provide all of the expected information during analysis. This limitation was documented rather than treating the missing information as evidence.

Other artifacts were therefore used to provide additional context about user activity on the system.

## 7. Evidence

Registry Explorer screenshots and relevant registry artifacts are stored in this directory as supporting evidence for the analysis.

## 8. Findings

The Registry analysis provided supporting information about the Windows system and its configuration.

Registry locations relevant to persistence and user activity were reviewed and considered alongside the other evidence collected during the investigation.

The registry findings will be correlated with Windows Event Logs, memory analysis, and timeline reconstruction to establish the sequence of events.

## 9. Conclusion

Registry analysis provided useful supporting evidence during the investigation.

Although some registry artifacts had limitations, the available evidence was retained and considered together with the other forensic artifacts rather than relying on a single source.

The results from this stage will be used during the timeline reconstruction and MITRE ATT&CK mapping.
