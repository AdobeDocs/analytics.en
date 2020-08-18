---
title: Log file
description: Obtain a log file for troubleshooting purposes.
---

# Log file

When troubleshooting issues with Ad Hoc Analysis, it is sometimes necessary to obtain its log file. Adobe can use the log file to locate the root cause of the issue and provide a resolution. The `discover.log` file contains all user interactions, report loading information, and Java error messages across all sessions. It hashes any protected information, such as the user's password. Large log files are split into 10 MB increments. When providing Adobe with the log files, ensure that all files are selected.

## Windows

Obtain the `discover.log` file for Windows:

1. Click the start menu and select **Run**, or press `[Win]` + `[R]`.
2. Paste the following into the text field, and click **OK**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Highlight all files in the folder, then right-click and choose **Send to > Compressed (zipped) Folder**.
4. Provide the Adobe representative with the .zip file.

## Mac

To obtain the `discover.log` file for Mac OS, do the following:

1. Open the Finder and navigate to `/Users/your-user/.adobe/Discover/log`
2. Highlight all files in the folder, then right-click and choose **Compress**.
3. Provide the Adobe representative with the .zip file.

If the total size for a compressed files exceeds 10 MB, an Adobe representative can provide a temporary FTP location.
