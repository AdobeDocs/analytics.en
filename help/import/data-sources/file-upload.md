---
title: Upload data sources file to Adobe
description: The process to upload a data sources file to Adobe Analytics for ingestion.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
---
# Upload data sources file to Adobe

Sending a data sources file to Adobe involves a typical authenticated FTP workflow. You can use Windows Explorer, Finder, or a dedicated FTP client to upload the desired files to Adobe's FTP location.

Locate the FTP credentials in the [Data sources manager](manage.md). Each data source has a link to its **[!UICONTROL FTP Info]**. Each FTP location is dedicated to that specific data source; you cannot use the same FTP location for multiple data sources.

For security reasons, FTP locations without any activity for 30+ days are disabled.

## The `.fin` file

A vital part of successfully ingesting a data sources file is the inclusion of a `.fin` file. This file indicates to Adobe that the data file is ready for processing. If you upload a data sources file without a corresponding `.fin` file, Adobe never processes that data.

The `.fin` file has the following properties:

* The file has a `.fin` extension. Make sure that your operating system allows you to see and edit file types.
* The file is empty. Do not store data inside the `.fin` file.
* The file has the exact same name as the data sources file. For example, if you upload a data sources file named `example.txt`, the `.fin` file **must** be named `example.fin`. If they are not identically named, Adobe never processes the data sources file.

Once both the data source file and `.fin` file are uploaded to the FTP site, Adobe processes the file. Do not upload the `.fin` file until the data sources file is fully uploaded. If the `.fin` file is prematurely uploaded, Adobe retrieves and ingests the partially uploaded file, throwing possible errors.

## Processing order

If you upload multiple files at the same time to the FTP site, Adobe ingests them in alphanumeric order. If your organization requires files to be ingested in a specific order, make sure that their file names are named alphanumerically.

## Processing time

To ensure the fastest processing of files, Adobe recommends aggregating metric data into a single row per date. For example, this data sources file, while valid, would be processed slower:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

This file would be processed faster, which contains the same data:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
