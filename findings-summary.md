# Findings Summary

## Partition and File System Findings
Sleuth Kit was used to identify the partition offset and file system details of the Linux forensic image. This provided the foundation for later file system and metadata analysis.

## Timeline Findings
Timelines created from `fls` and `ils` output helped reconstruct file activity around the suspected event window. This made it easier to identify suspicious access, modification, and deletion activity.

## Inode and Symlink Findings
Inode analysis identified symbolic link activity from the contractor’s folder to the confidential spreadsheet. This was a key artifact because it connected user-access behavior to the target file.

## File Permission Findings
The confidential spreadsheet had permissions that allowed users outside the owner account to read the file. This explained how the contractor could access the document even though it was intended to be confidential.

## Autopsy Validation
Autopsy was used to validate file metadata, image details, file categorization, and activity timelines. Windows Autopsy provided a more modern interface and richer artifact views, while Linux Autopsy stayed closer to the underlying Sleuth Kit workflow.

## Overall Conclusion
The investigation found evidence suggesting suspicious access behavior involving the confidential spreadsheet. The strongest evidence came from correlating symlink activity, timestamps, inode metadata, and permissive file permissions.
