---
description: Information about the requirements for your report suite before using Data Sources.
subtopic: Data sources
title: Requirements and upload limits
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 97a7cc65-f99a-4227-94f2-6f428ebdfad3
---
# Requirements and upload limits

Information about the requirements for your report suite before using Data Sources.

The following sections list constraints that apply to Data Sources and data imported into marketing reports and analytics.

* [Size Limits](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18) 
* [Dates](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2) 
* [General](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF) 
* [Multi-Byte Support](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22) 
* [Uploading Web Log Files](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Size Limits {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Each FTP account is limited to 50 MB of total data for all files. Processing pauses if the size exceeds 50 MB and does not resume until the total is below 50 MB.

## Dates {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Each calendar day you can upload data for 90 unique dates. If you exceed this limit, the upload will fail with an error message stating that you have ?exceeded the maximum unique days.
* Only data with current or past dates can be imported. Do not attempt to use future dates in your Data Sources data.
* All rows must have a date specified to enable report graphing capabilities. If a row does not include a date, Data Sources generates an error and rejects the file. The date/time format varies by data source type:

    * **Full Processing Data Sources**: Use the ISO 8601 date format of `YYYY-MM-DDThh:mm:ss±UTC_offset` (for example, `2013-09-01T12:00:00-07:00`), or Unix Time Format (the number of seconds elapsed since January 1, 1970).
    
    * **Standard and Integration Data Sources**: Use the following date format: `MM/DD/YYYY/HH/mm/SS` (for example, `01/01/2013/06/00/00`)

## General {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* When you upload a Data Sources file, Data Sources performs basic data validation to make sure the file does not contain formatting errors. If an error is encountered in a file, an email notification is sent and processing stops.
* Data fields cannot contain semi-colons. Data Sources skips records that contain a semi-colon.
* Data from Web Log, Traffic, and some Generic Data Sources groupings are not available in Data Warehouse or Discover. For more information, see [Data Types and Categories](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* Data Sources do not support serialized events.

## Multi-Byte Support {#section_96C8D26B21184C3E839865DB6F23EA22}

Data Sources supports multi-byte encoding. Data Sources attempts to detect the format of the incoming Data Sources file, and when necessary, converts it to a supported format. The following table lists common character formats and their support status.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Character Format </th> 
   <th colname="col2" class="entry"> Support </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Supported. The report suite used with Data Sources must have multi-byte character support enabled. </p> <p>See <a href="https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html"  > New Report Suite</a> in Help </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 with Byte Order Mark (EF BB BF) </td> 
   <td colname="col2"> <p>Supported. This format is non-standard, though many Windows applications save in this format. </p> <p>For example, WordPad saves in this format if you pick "UTF-8". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (aka Latin-1 or Windows-1252) </td> 
   <td colname="col2"> Supported. Microsoft Excel saves in this format when you pick a "tab delimited" export. The Report suite must be using the ISO-8859-1 locale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, with Byte Order Mark (FF FE) </td> 
   <td colname="col2"> Converted to ISO-8859-1 or UTF-8, as determined by your report suite configuration. Microsoft Excel saves in this format when you pick a unicode export. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, with Byte Order Mark (EF FF) </td> 
   <td colname="col2"> Converted to ISO-8859-1 or UTF-8, as determined by your report suite configuration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 with no byte-order mark </td> 
   <td colname="col2"> Not supported. </td> 
  </tr> 
 </tbody> 
</table>

If you submit a UTF-8 or ISO-8859-1 file and your report suite is not configured to support it, one of the following happens:

* The error is detected during conversion, in which case you receive a message like "Found bad character in file at position 18 while converting from UTF-8 to ISO-8859-1".
* The file is processed with no errors, but you see garbled data in the report.

## Uploading Web Log Files {#section_DD736FC971FE45C89AB310BEDC1FE707}

* The most useful reports for viewing Web Log data are traffic reports, such as page views.
* Page names are displayed as the entire URL, including the query-string.
* Each file request appears as a separate page view, including style sheets and image files.
* If you append information to the URL, files might be recorded as separate pages. For example, Adobe records the following URLs as two separate pages:

`/jokes/misc/snail_joke.html?userid=12345`

`/jokes/misc/snail_joke.html?userid=98765`
