# Methodology

## 1. Image Verification
The forensic image was validated using provided MD5 and SHA1 hash values to confirm evidence integrity before analysis.

## 2. Partition Analysis
The partition layout was reviewed using `mmls` to identify the starting sector offset needed for Sleuth Kit analysis.

## 3. File System Analysis
The file system was reviewed using `fsstat` to determine the file system type, block size, and structural details.

## 4. Read-Only Mounting
The image was mounted using read-only forensic mount options to safely inspect file contents without modifying evidence.

## 5. Timeline Generation
The `fls` tool was used to list deleted files and directories in body-file format. The output was processed with `mactime` to create a file activity timeline.

## 6. Inode-Based Analysis
The `ils` tool was used to list inode information. The resulting body file was processed with `mactime` to compare inode-based activity with filename-based activity.

## 7. Metadata and Block Review
Several Sleuth Kit tools were used for deeper analysis:
- `istat` to view inode metadata
- `icat` to extract file content from an inode
- `ffind` to map an inode to a filename
- `blkcat` to dump block content
- `ifind` to identify which inode referenced a data block

## 8. Autopsy Validation
The image was loaded into Autopsy to validate partition information, file system metadata, file activity, and file type categorization.

## 9. Permissions Review
The confidential spreadsheet’s permissions were reviewed to determine why another user could access the file.

## 10. Case Conclusion
Findings from timestamps, symlink activity, inode metadata, and file permissions were correlated to determine whether suspicious access occurred.
