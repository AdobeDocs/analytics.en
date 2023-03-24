---
title: Upload data sources file to Adobe
description: Learn the process to upload a data sources file to Adobe Analytics.
---

# Upload data sources file to Adobe

Sending a data sources file to Adobe involves a typical authenticated FTP workflow. You can use Windows Explorer, Finder, or a dedicated FTP client to upload the desired files to Adobe's FTP location.

Locate the FTP credentials in the [Data sources manager](manage.md). Each data source has a link to its **[!UICONTROL FTP Info]**.

## The `.fin` file

A vital part of successfully ingesting a data sources file is the inclusion of a `.fin` file. This file indicates to Adobe that the data file is ready for processing. If you upload a data sources file without a corresponding `.fin` file, Adobe never processes that data.

The `.fin` file has the following properties:

* The file has a `.fin` extension. Make sure that your operating system allows you to see and edit file types.
* The file is empty. Do not store data inside the `.fin` file.
* The file has the exact same name as the data sources file. For example, if you upload a data sources file named `example.txt`, the `.fin` file **must** be named `example.fin`. If they are not identically named, Adobe never processes the data sources file.

Once both the data source file and `.fin` file are uploaded to the FTP site, Adobe processes the file. Do not upload the `.fin` file until the data sources file is fully uploaded. If the `.fin` file is prematurely uploaded, Adobe retrieves and ingests the partially uploaded file, throwing possible errors.

## Next steps

[Troubleshooting](troubleshooting.md): Learn how to resolve potential issues when executing a data sources workflow.
