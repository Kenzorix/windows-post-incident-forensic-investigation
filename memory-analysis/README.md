# Memory Analysis

## 1. Purpose

Memory analysis was carried out to examine the volatile data captured from the Windows 10 victim machine.

The purpose was to identify useful information from the memory image that could support the investigation and provide additional context alongside the disk and Windows artifacts.

## 2. Tools Used

- WinPmem
- Volatility 3
- Python

## 3. Memory Acquisition

A memory dump was captured from the Windows 10 victim machine and saved as part of the case evidence.

The memory image was also hashed to help maintain the integrity of the captured evidence during analysis.

## 4. Volatility Analysis

I used Volatility 3 to examine the captured memory image.

The initial analysis included identifying the Windows information from the memory image before moving on to other available Volatility plugins.

This helped confirm that the memory image could be analysed with the selected Volatility framework.

## 5. Analysis Performed

The memory investigation focused on extracting information that could help identify processes, system activity, and other volatile evidence relevant to the case.

The results were considered alongside the disk image, registry artifacts, and Windows Security logs rather than being treated as standalone evidence.

## 6. Evidence

The following screenshots document the memory analysis:

a) `01_volatility-windows-info` — Windows information identified from the memory image.
b)`volatility_memory_analysis_completed` — supporting evidence from the Volatility analysis.

## 7. Limitations

Some Volatility analysis did not produce useful output during the investigation.

In particular, the timeline generation attempt did not return the expected results. This was documented as a limitation rather than treating the absence of output as evidence.

Other available forensic artifacts were therefore used to support the investigation and timeline reconstruction.

## 8. Conclusion

Memory analysis provided additional volatile evidence for the investigation and helped support the overall forensic examination.

The memory findings were considered together with the registry, event logs, and disk artifacts to build a more complete picture of activity on the victim system.
