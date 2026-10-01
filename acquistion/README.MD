# Evidence Acquisition
This was the first stage of the investigation,
I acquired the Windows 10 victim machine so I could work on a copy of the evidence instead of analyzing the original system directly.

## Disk Acquisition
I used FTK Imager to acquire the Windows 10 disk.
- Tool: FTK Imager
- Image format: E01
- Case: CASE-001

The acquired image was saved to external storage and used for the rest of the disk investigation.

## Memory Capture
I also captured the memory from the Windows 10 victim machine.

The memory dump was saved as:
`CASE-001.mem`
I kept the memory capture for later analysis with Volatility 3.

## Hashing
I generated hashes for the evidence collected during the acquisition stage. The hashes were recorded so I could verify the integrity of the evidence during the investigation.

## Evidence Collected
- Windows disk image (E01)
- Memory dump (`CASE-001.mem`)
- Evidence hashes

The acquired evidence was then moved to the analysis stage.
