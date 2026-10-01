# Timeline Analysis
## 1. Purpose
Timeline analysis was used to arrange relevant forensic events by time and help reconstruct the sequence of activity on the Windows 10 victim machine.

The timeline was intended to correlate evidence from different sources and provide a clearer view of what happened during the investigation.

## 2. Tools Used

- Volatility 3
- Windows Event Logs
- KAPE-collected artifacts
- Registry artifacts

## 3. Timeline Generation

I attempted to generate a timeline from the captured memory image using Volatility 3.

The timeline generation did not produce the expected output during the investigation.

This was documented as a limitation rather than treating the lack of output as evidence.

## 4. Timeline Reconstruction

Since the automated timeline did not produce the expected results, relevant timestamps from the available forensic artifacts were considered separately.

The Windows Security logs provided authentication-related timestamps, while other collected artifacts provided additional information that could be correlated with the investigation.

## 5. Evidence Correlation
The timeline investigation was correlated with:

- Event ID 4625
- Registry artifacts
- KAPE-collected artifacts
- Memory analysis
- Other available forensic evidence

Correlating these sources helped provide context around the activity observed on the victim machine.

## 6. Limitations
The Volatility timeline generation did not return the expected results in the lab environment.

Because of this, a complete automated timeline could not be established from the memory image alone.

The available event logs and other forensic artifacts were therefore used to support the reconstruction of events.

## 7. Conclusion
Timeline analysis helped organize the available evidence by time and provided a basis for correlating activity across different forensic artifacts.

Although the automated Volatility timeline was unsuccessful, the remaining evidence was retained and considered during the overall incident reconstruction.
