# Event Log Analysis

## 1. Purpose

After collecting the Windows artifacts, I reviewed the Windows Security logs to identify authentication-related activity on the victim machine.

The main focus was on failed logon events that could provide useful information for reconstructing the incident.

## 2. Tool Used

- Windows Event Viewer

## 3. Security Log Analysis

I reviewed the Windows Security log and filtered the events using Event ID 4625.

Event ID 4625 represents a failed logon attempt.

The initial Security log contained a large number of events, so filtering was used to narrow the investigation to the relevant authentication events.

## 4. Event ID 4625 Findings

The filter returned 41 events associated with Event ID 4625.

The events were recorded as Audit Failure events under the Logon task category.

A selected event was examined in more detail to understand the authentication attempt and the information recorded by Windows.

Some of the details observed included:

- Target username: Kenzorix
- Logon Type: 2
- Logon Process: User32
- Authentication Package: Negotiate
- Process: C:\Windows\System32\svchost.exe
- IP Address: 127.0.0.1

## 5. Evidence

The following screenshots document the Event ID 4625 investigation:

- `EVENT_4625_FILTERED.png` — filtered Security log showing the 4625 events.
- `EVENT_4625_DETAILS.png` — details of a selected 4625 event.

## 6. Analysis

The presence of multiple failed logon events was recorded as part of the authentication activity observed on the system.

The selected event showed a Logon Type of 2, which indicates an interactive logon attempt.

The source address shown for the selected event was 127.0.0.1, indicating that this particular event originated locally on the system.

These observations will be correlated with other forensic artifacts before drawing conclusions about the activity.

## 7. Conclusion

The Windows Security log provided useful authentication evidence for the investigation.

The Event ID 4625 events were documented and will be correlated with the registry artifacts, memory evidence, and timeline during the later stages of the investigation.
