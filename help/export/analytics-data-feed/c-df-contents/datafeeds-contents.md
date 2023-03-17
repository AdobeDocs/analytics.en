---
description: This section describes the files found in a data feed delivery.
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: Data Feed contents - overview
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
---
# Data Feed contents - overview

This section describes the files found in a data feed delivery.

## Manifest file {#feed-manifest}

The manifest file contains the following details about each file that is part of the uploaded data set:

* File name
* File size
* MD5 hash
* Number of records contained in the file

The manifest file follows the same format as a Java JAR manifest file.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. Manifest files are named according to the following:

```text
[rsid]_[YYYY-mm-dd].txt
```

A typical manifest file contains data similar to the following:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Every manifest file contains a header, indicating the total number of lookup files, data files, and total number of records in all data files. This header is followed by multiple sections containing information for each file included in the data feed delivery.

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Lookup files

Some data feed columns output a number that corresponds to its actual value. Lookup files are used to match a number from a data feed column and match it to an actual value. For example, a value of "497" in the `browser` hit data column indicates that the hit came from "Microsoft Internet Explorer 8" if you look in `browser.tsv`.

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Other files, such as `browser.tsv`, are generic.

The lookup files are delivered together in a compressed zip named according to the following:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
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

## Hit data files

Hit data is provided in a [!DNL hit_data.tsv] file. The amount of data in this file is determined by the delivery format (hourly or daily, and single or multiple files). This file contains only hit data. The column headers are delivered separately with the lookup files. Each row in this file contains a single server call.

Files delivered by Adobe vary based on the type of data feed that you have configured. All files are encoded using ISO-8859-1.

* `[rsid]` refers to the report suite ID the data feed is from.
* `[index]` is used only in multiple file feeds, and refers to the correct order of paginated files.
* `[YYYY-mm-dd]` refers to the starting day the data feed is for.
* `[HHMMSS]` is used only in hourly feeds, and refers to the starting hour the data feed is for.
* `[compression_suffix]` refers to the type of compression used. Typically data feeds are compressed into `tar.gz` or `zip` files.

### Daily, single file

After data is collected for a day, you receive a single compressed data file and a manifest file. The data file is named:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

When extracted, the data file contains a single `hit_data.tsv` file with all data for that day, as well as lookup files for any required columns.

### Daily, multiple files

After data is collected for a day, you receive one or more compressed data files and a manifest file. The data file is named:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

When extracted, each data file contains a single `hit_data.tsv` that contains approximately 2GB of uncompressed data, as well as lookup files for any required columns.

### Hourly, single file

After data is collected for an hour, you receive a single compressed data file and a manifest file. The data file is named:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

When extracted, the data file contains a single `hit_data.tsv` file with all data for that hour, as well as lookup files for any required columns.

### Hourly, multiple files

After data is collected for an hour, you receive one or more compressed data files and a manifest file. The data file is named:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

When extracted, each data file contains a single `hit_data.tsv` that contains approximately 2GB of uncompressed data, as well as lookup files for any required columns.

## Data file size

The hit data file size varies greatly depending on the number of variables actively used and amount of traffic sent to report suite. However, on average, a row of data is approximately 500B (compressed) or 2KB (uncompressed). Multiplying this by the number of server calls can provide a rough estimate on how large a data feed file is. Once your organizations starts receiving data feed files, you can find a more accurate number by dividing the number of rows in `hit_data.tsv` by its total file size.
