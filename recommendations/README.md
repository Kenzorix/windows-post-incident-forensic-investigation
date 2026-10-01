# Recommendations

## 1. Overview
Based on the evidence collected during the investigation, the following recommendations are provided to reduce the risk of similar activity and improve the ability to detect and investigate future incidents.

## 2. Monitor Registry Persistence
Security teams should monitor Registry locations commonly used for persistence, especially:

`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

Unexpected or unauthorized entries should be investigated and validated against known software.

## 3. Monitor Suspicious Script Execution
Batch files and command interpreters such as `cmd.exe` should be monitored when they are launched from unusual locations or through persistence mechanisms.

In this case, the Registry entry launched a batch file from the user's Downloads directory.

## 4. Improve Windows Event Log Monitoring
Windows Security logs should be centrally collected and monitored for repeated authentication failures.

Event ID 4625 can be used as one of the indicators for investigating failed logon activity, especially when multiple events occur within a short period or show unusual characteristics.

## 5. Protect Forensic Evidence

Forensic evidence should be acquired using appropriate forensic procedures and hashed after acquisition.

Original evidence should be preserved while analysis is performed on working copies.

## 6. Maintain Endpoint Visibility

Security monitoring should include useful endpoint telemetry such as process execution, Registry changes, authentication events, and other Windows security events.

This can improve the ability of SOC and DFIR teams to correlate activity during an investigation.

## 7. Regularly Review Persistence Locations
Organizations should periodically review common Windows persistence locations and investigate entries that are not associated with approved applications or administrative activity.

## 8. Incident Response Documentation

Investigation activities, evidence collected, hashes, timestamps, tools used, findings, and limitations should be documented throughout the investigation.

This helps maintain a clear chain of reasoning and makes the investigation easier to review or reproduce.

## 9. Conclusion

The investigation demonstrated the importance of combining multiple forensic sources rather than relying on a single artifact.
Registry analysis, event logs, memory analysis, and other Windows artifacts should be correlated when investigating suspected endpoint compromise.
