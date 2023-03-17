---
title: Classification importer troubleshooting
description: Common upload issues when using the classification importer.
feature: Classifications
exl-id: de3e9eca-9264-4711-b73a-4a1a3dd16715
---
# Classification importer troubleshooting

The most common issues when uploading classification data to Adobe.

## Incorrect file format or extension

Classifications require a specific file type and format to upload successfully. If saved improperly, it throws an error and doesn't process any rows. The error returned is frequently *"First column is required to be the key"*, but can be any number of errors. Be sure to check the following:

* **Uploading a spreadsheet (.xlsx) instead of a .tab or .txt file**: You can get the error message *"The first column is required to be the key"* when you upload classification files in an incorrect format. The classification importer does not know how to handle .xls or .xlsx files. When in the 'Save As' dialogue in Excel, set the correct Save as type:
  * On Windows, use the file format `Text (Tab delimited) (*.txt)`
  * On Mac, use the file format `Windows Formatted Text`.
* **Changing the filename extension after saving it as a workbook**: Attempting to directly rename a file extension generates an invalid workbook. Only use Excel's Save As function or edit classifications in a text editor such as Notepad++.
* **Using uppercase extensions**: Uppercase extensions (such as `fileupload.TXT`) don't work. Rename the file to a lowercase extension (`fileupload.txt`).
* **Mismatched character encoding**: Be sure that the encoding of the saved classification upload matches the original encoding when the template was downloaded. If you upload a UTF-16 file when it was originally encoded in UTF-8, uploads produce unexpected results. Adobe recommends uploading files using UTF-8 without byte order marks.

## Invalid file contents

If your upload file is correctly formatted, the uploader attempts to import as many valid rows as possible. Some common issues with classification data:

* **Rows that are already classified**: When attempting to upload rows that are already classified with the same value, the importer returns rows that had no effect. This outcome is expected, as classifications don't reclassify a key value with the same classification. It is a notification instead of an error. It is not anything to worry about if you do not alter all rows within an export file. Adobe recommends only uploading changed rows.
* **Header does not match the variable being uploaded**: If you download a classification template for the Tracking code dimension and attempt to upload it to an eVar classification, it fails. Only use export files for the specific variables they were exported from.
* **A key or classification value contains the value 0**: Classifications cannot differentiate the value 0 from a blank cell, so it cannot classify this value. See [Classifications FAQ](../faq.md).
* **The classification file contains commas or special characters**: See [Classifications FAQ](../faq.md).
* **Extra tabs in the uploaded file**: Sometimes when editing classification files, an extra tab can be accidentally slipped in. Each row requires an identical number of tabs to process correctly. To check for extra tabs within the file, highlight all text in a plaintext editor and make sure that no rows have extra space at the end.
* **Duplicate key values exist in the file**: Each key value can only have one classification per column. If you attempt to classify the same value multiple times, the importer throws an error.
* **Subclassifications exist and are incorrectly configured**: If subclassifications exist, check the following:
  * All subclassification values have a parent classification value
  * No two subclassifications reference the same parent classification value
* **Column mismatch**: You can get the error message *"The key on line has too many columns"* if there are an invalid number of columns on any given row. For example, you have 3 columns in your classification upload and the variable only has a single classification. Validate your upload file to make sure that the number of columns are not greater than the number of classifications configured for that variable.

## Troubleshoot FTP imports

The following are common causes behind FTP classifications not processing uploaded files:

* **Missing .fin file**: Create a blank text document on your desktop and rename the filename extension from .txt to .fin. The name of this .fin file must match the name of the classification file in question. For example, if your FTP filename is `fileupload.tab`, name your .fin file `fileupload.fin`. Once the .fin file is uploaded, both files disappear.
* **Uploading .fin file before classification file**: Sometimes a .fin is created before the classifications file is finished uploading to the FTP site. Processing can fail when files are uploaded out of order. Remove both files, add the classification file first, then the .fin file after the classification file is fully uploaded.
* **File size is excessively large**: Adobe recommends keeping classification file sizes as small as possible to ensure expeditious processing.
* **Existing files already processing**: If multiple files are uploaded for the same variable and report suite, the old file stops processing in favor of the new one. If uploading classifications using multiple files, wait for confirmation that existing files have finished processing before uploading new ones.
* **Uploaded files not placed in root directory**: Files uploaded to Adobe's FTP site must be placed in the root directory. If classification import files are placed in subfolders, they are not picked up or processed. 

If you still have issues uploading a classification file, contact Adobe Customer Care.
