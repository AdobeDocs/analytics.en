---
title: Mobile attributes lookup
description: Lookup file for mobile attributes.
feature: Data Feeds
exl-id: d5130716-2bf2-42ce-811e-26a5081efc18
---
# Mobile attributes lookup

Mobile attributes show properties of the mobile device in the hit. This file appears when:

* The data feed is configured to send mobile attributes. This setting is not available in the product UI, and instead must be enabled by Customer Care. If you want to use mobile attributes in a data feed, contact Customer Care with the desired feed ID and request to enable "Dynamic lookups".
* The `mobile_id` column is included.
* The columns `user_agent`, `ch_hdr`, and `ch_js` are **excluded**. These exclusions are required due to licensing agreements with DeviceAtlas.

Download [`mobile_attributes_headers.tsv`](assets/mobile_attributes.tsv), or reference the list here:

* `mobile_id`
* `Manufacturer`
* `Device`
* `Device Type`
* `Operating System`
* `Diagonal Screen Size`
* `Screen Height`
* `Screen Width`
* `Cookie Support`
* `Color Depth`
* `MP3 Audio Support`
* `AAC Audio Support`
* `AMR Audio Support`
* `Midi Monophonic Audio Support`
* `Midi Polyphonic Audio Support`
* `QCELP Audio Support`
* `GIF87 Image Support`
* `GIF89a Image Support`
* `PNG Image Support`
* `JPG Image Support`
* `3GPP Video Support`
* `MPEG4 Video Support`
* `3GPP2 Video Support`
* `WMV Video Support`
* `MPEG4 Part 2 Video Support`
* `Stream MP4 AAC LC Video Support`
* `Stream 3GP H264 Level 10b Video Support`
* `Stream 3GP AAC LC Video Support`
* `3GP AAC LC Video Support`
* `Stream MP4 H264 Level 11 Video Support`
* `Stream MP4 H264 Level 13 Video Support`
* `Stream 3GP H264 Level 12 Video Support`
* `Stream 3GP H264 Level 11 Video Support`
* `Stream 3GP H264 Level 10 Video Support`
* `Stream 3GP H264 Level 13 Video Support`
* `3GP AMR NB Video Support`
* `3GP AMR WB Video Support`
* `MP4 H264 Level 11 Video Support`
* `3GP H263 Video Support`
* `MP4 H264 Level 13 Video Support`
* `Stream 3GP H263 Video Support`
* `Stream 3GP AMR WB Video Support`
* `3GP H264 Level 10b Video Support`
* `MP4 ACC LC Video Support`
* `Stream 3GP AMR NB Video Support`
* `3GP H264 Level 10 Video Support`
* `3GP H264 Level 13 Video Support`
* `3GP H264 Level 11 Video Support`
* `3GP H264 Level 12 Video Support`
* `Stream HTTP Live Streaming Video Support`
