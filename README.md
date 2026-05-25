# Linux Forensic Analysis Using Sleuth Kit and Autopsy

## Overview
This project documents a Linux forensic investigation completed in a controlled academic lab environment. The investigation used Sleuth Kit command-line tools and Autopsy to analyze a Linux disk image, examine file system metadata, generate forensic timelines, review inode activity, and determine whether a user may have accessed a confidential spreadsheet.

## Objective
The objective was to analyze a Linux forensic image and identify evidence suggesting whether a contractor accessed a confidential financial document. The investigation focused on partition analysis, file system review, timeline generation, inode analysis, deleted-file review, file permissions, and Autopsy validation.

## Scenario
A Linux-based file server contained user folders for employees and contractors. The investigation focused on whether a contractor may have accessed a confidential financial spreadsheet belonging to another user.

## Tools Used
- SIFT Workstation
- Sleuth Kit
- Autopsy for Linux
- Autopsy for Windows
- Linux command line
- mmls
- fsstat
- fls
- ils
- mactime
- istat
- icat
- ffind
- blkcat
- ifind

## Skills Demonstrated
- Linux forensic image analysis
- Partition offset identification
- File system analysis
- Read-only forensic mounting
- Inode and metadata analysis
- Deleted-file and directory review
- Timeline generation using mactime
- Symlink analysis
- File permission review
- Autopsy case creation and validation
- Evidence-based forensic reporting

## Methodology
1. Verified the forensic image using provided hash values.
2. Identified the partition layout and starting offset using Sleuth Kit.
3. Determined the Linux file system type and block size.
4. Mounted the forensic image read-only for safe examination.
5. Used `fls` and `ils` to identify file system and inode-based activity.
6. Generated timelines using `mactime`.
7. Used `istat`, `icat`, `ffind`, `blkcat`, and `ifind` to examine inode and block-level evidence.
8. Loaded the image into Autopsy to validate file system metadata and file activity.
9. Compared Linux Autopsy and Windows Autopsy features.
10. Wrote a case conclusion based on symlink activity, timestamps, and file permissions.

## Key Findings
- Timeline analysis showed suspicious activity around the confidential spreadsheet.
- Inode analysis identified a symbolic link from the contractor’s folder to the confidential file.
- Metadata showed access, modification, and deletion activity around the suspected event window.
- File permissions allowed other users to read the confidential file.
- Autopsy validation supported the command-line findings.

## What I Learned
This lab strengthened my understanding of Linux forensic workflows, especially how file system metadata, inodes, symbolic links, timelines, and permissions can be used to reconstruct user activity. It also showed how command-line forensic tools and GUI tools like Autopsy can complement each other during an investigation.

## Disclaimer
This project was completed in a controlled academic lab environment using a provided forensic training image. No real personal, confidential, or production data is included in this repository.
