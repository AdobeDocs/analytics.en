---
description: This section describes the files found in a data feed delivery.
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
seo-description: This section describes the files found in a data feed delivery.
seo-title: Data Feed contents - overview
solution: Analytics
subtopic: data feeds
title: Data Feed contents - overview
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
---

# Data Feed contents - overview

This section describes the files found in a data feed delivery.

## Manifest File {#section_044BBDE2906D49518F8264CD4832D429}

The manifest file contains the following details about each file that is part of the uploaded data set:

* file name 
* file size 
* MD5 hash 
* number of records contained in the file

The manifest file follows the same format as a Java JAR manifest file.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. Manifest files are named according to the following:

```
<report_suite_id>_YYYY_MM_DD.txt
```

A typical manifest file contains data similar to the following:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Every manifest file contains a header, indicating the total number of lookup files, data files, and total number of records in all data files. This header is followed by multiple sections containing information for each file included in the data feed delivery.

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Lookup Files {#section_B5863537A48D47D78D0F7274838923C1}

Lookup files do not contain hit data, these are supplemental files that provide the column headers for the hit data, and lookup files to translate the IDs found in the data feed to actual values. For example, a value of "497" in the browser column indicates that the hit came from "Microsoft Internet Explorer 8".

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Other files, such as `browser.tsv`, are generic.

The lookup files are delivered together in a compressed zip named according to the following:

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
```

* [!DNL column_headers.tsv] (customized for this data feed)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (customized for this data feed)

## Hit Data Files {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. The amount of data in this file is determined by the delivery format (hourly or daily, and single or multiple files). This file contains only hit data. The column headers are delivered separately with the lookup files. Each row in this file contains a single server call.

## Delivery Contents {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>The files are encoded using ISO-8859-1.

The actual files delivered by Adobe vary based on the type of data feed that you have configured. Find the configuration that matches your data feed in the following table for a description of the delivered files.

The time (HHMMSS) indicated in a file name always indicates the beginning of the date range for the data in the file, regardless of when the file was produced or uploaded. 

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Delivery Format </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Daily, single file </td> 
   <td colname="col2"> <p>After data is collected for a day, you will receive a delivery that contains the following: </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">a single compressed data file. </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">A manifest file. </li> 
    </ul> <p>The data file is delivered with the following name: </p> 
    <code>
      &lt;report_suite&gt;_&lt;YYYY-mm-dd&gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, the data file contains a single <span class="filepath"> hit_data.tsv</span> file with all data for that day, as well as the compressed lookup files described above. </p> <p>The hit data file size varies greatly depending on the number of variables actively used and amount of traffic on the report suite. However, on average, a row of data is approximately 500B (compressed) or 2KB (uncompressed). Multiplying this by the number of server calls can provide a rough estimate on how large a data feed file will be. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Daily, multiple file </td> 
   <td colname="col2"> <p>After data is collected for a day, you will receive a delivery that contains the following: </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">One or more compressed data files, broken into 2 GB chunks. </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">A manifest file. </li> 
    </ul> <p>Each data file is delivered with the following name: </p> 
    <code>
      &lt;index&gt;-&lt;report_suite&gt;_&lt;YYYY-mm-dd&gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;index&gt;</code> is an incrementing file index from <i>1</i> to <i>n</i>, given <i>n</i> files, and <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, each data file contains a single <span class="filepath"> hit_data.tsv</span> that contains approximately 2 GB of uncompressed data, as well as the compressed lookup files described above. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hourly, single file </td> 
   <td colname="col2"> <p>After data is collected for an hour, you will receive a delivery that contains the following: </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">a single data file. </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">A manifest file. </li> 
    </ul> <p>The data file is delivered with the following name: </p> 
    <code>
      &lt;report_suite&gt;_&lt;YYYY-mm-dd&gt;-&lt;HHMMSS&gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, the data file contains a single <span class="filepath"> hit_data.tsv</span> file with all data for that hour. The compressed lookup files described above are delivered only with the data for the first hour of each day. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hourly, multiple file </td> 
   <td colname="col2"> <p>After data is collected for an hour, you will receive a delivery that contains the following: </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">One or more compressed data files, broken into 2 GB chunks. </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">A manifest file. </li> 
    </ul> <p>Each data file is delivered with the following name: </p> 
    <code>
      &lt;index&gt;-&lt;report_suite&gt;_&lt;YYYY-mm-dd&gt;-&lt;HHMMSS&gt;.tsv.&lt;compression_suffix&gt;
    </code> <p>Where <code> &lt;index&gt;</code> is an incrementing file index from <i>1</i> to <i>n</i>, given <i>n</i> files, and <code> &lt;compression_suffix&gt;</code> is either <code> gz</code> or <code> zip</code> </p> <p>When extracted, each data file contains a single <span class="filepath"> hit_data.tsv</span> that contains approximately 2 GB of uncompressed data. The compressed lookup files described above are delivered only with the data for the first hour of each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

