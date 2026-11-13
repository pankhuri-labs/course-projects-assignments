# Digital Forensics: Steganography and Deleted-File Recovery

**Course:** Professional Certificate Programme in Cybersecurity and AI, IIT Madras · **Type:** Graded mini project (week 28) · **Year:** 2026

> **Summary:** Hid a secret message inside an image, permanently deleted the file, then recovered it from a forensic disk image and decoded the message. Shows the core forensic principles behind incident response: preserve evidence first, analyse a copy, and never assume "deleted" means gone.

## Objective
Simulate a forensic investigation of concealed and destroyed evidence on an NTFS volume.

## Approach
- Set up separate NTFS partitions on a Windows Server 2022 VM for the data and the evidence.
- Used SilentEye to embed a hidden text message in a JPG, saved it to the data partition and deleted it with Shift+Delete (bypassing the Recycle Bin).
- Used FTK Imager to create a forensic image of the logical drive in E01 format on the evidence partition.
- Opened a case in Autopsy, found the deleted file and recovered the JPG.
- Decoded the hidden message from the recovered image with SilentEye.

## Outcome
The deleted image was recovered intact and the concealed message decoded, confirming that the data stayed on disk after deletion and that imaging preserved the evidence for analysis.

## Tools
FTK Imager 8.2.0, Autopsy, SilentEye 0.4.1, Windows Server 2022, VMware Workstation

## Files
- [`forensic_recovery_steganography_report.pdf`](forensic_recovery_steganography_report.pdf): step-by-step report with screenshots
