---
title: Dynamic lookups
description: Learn about what dynamic lookups are and how to enable them. Includes carriers, mobile attributes, and operating system types.
exl-id: 644bf34b-312d-483a-a590-2dd8d6a773a5
feature: Data Feeds
---
# Dynamic lookups

Dynamic lookups allow you to receive additional lookup files in your data feed otherwise not available. This setting enables the following lookup tables to be sent with each data feed file:

* **Carrier name**: Provides additional context for the `carrier` column. The file name included is `carrier.tsv`.
* **Mobile attributes**: Provides additional context for the `mobile_id` column, including all features tracked for each mobile device. The file name included is `mobile_attributes.tsv`.
* **Operating system type**: Provides an alternate context for the `os` column. Both `operating_systems.tsv` and `operating_system_type.tsv` use the `os` column as the key, however only `operating_system_type.tsv` is a dynamic lookup.

## Enable dynamic lookups

If you want to receive the lookup files mentioned, you must meet all the following prerequisites:

* The key column must be included in the data feed.
  * For `carrier.tsv`, you must include `carrier`.
  * For `mobile_attributes.tsv`, you must include `mobile_id`.
  * For `operating_system_type.tsv`, you must include `os`.
* The following columns must be **excluded**. If any of these columns are included in the data feed, the additional lookup tables are not included.
  * `user_agent`
  * `ch_hdr`
  * `ch_js`

Once your data feed meets the column inclusion and exclusion requirements, contact Customer Care with the data feed ID and request to enable dynamic lookups.

## Lookup header reference

Column headers for these lookup files do not change over time, so headers are not included in each data feed file. Use these column headers as a reference, or download their respective `.tsv` file.

+++**Carrier name**
Download [carrier_headers.tsv](assets/carrier_headers.tsv) or reference the headers below.

`carrier`
`Carrier Name`
+++

+++**Mobile attributes**
Download [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) or reference the headers below.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Operating system type**
Download [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) or reference the headers below.

`os`
`Operating System Type`
+++
