---
title: End-of-life for full processing data sources
description: Learn more about the end-of-life announcement for full processing data sources.
---

# End-of-life for full processing data sources

Full processing data sources has historically enabled organizations to submit hit-level data to Adobe Analytics. This data was processed in the same way as data collected through traditional data collection means, such as AppMeasurement. In 2020, Adobe released the [Bulk data insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), which performs the same functions as full processing data sources, but with additional features. This page provides details about additional functionality provided by the Bulk data insertion API and outlines differences in file formats.

On 25 March 2021, Adobe prevented new full processing data sources connections from being created. On 31 January 2022, all full processing data services were deactivated.

## Key differences between full processing data sources and the Bulk data insertion API

* Bulk data insertion allows you to submit multiple files for parallel processing. Visitor Groups ensure visitor continuity and eVar attribution.
* Bulk data insertion has data validation and error handling capabilities, removing some of the administrative work of submitting hit data.
* Bulk data insertion supports multiple visitor ID identification methods.
* Bulk data insertion has some additional required fields: A visitor identification column, a `pageName` (or link equivalent), `reportSuiteID`, `timestamp`, and `userAgent`.
* To ensure visitor continuity and attribution, Bulk data insertion requires rows within files to be sorted in chronological order. See [Visitor Groups](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) to learn about the ordering of Visitor activity across files.
* Bulk data insertion requires files to be .csv compressed in .gzip format.
* BDIA uses `timestamp` instead of `date`.

## Variable comparison between BDIA and full processing data sources

The following variables were introduced to Bulk data insertion, previously unavailable in full processing data sources:

* **`aamlh`**: Adobe Audience Manager location hint.
* **`contextData.key`**: [Context data variables](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: Experience Cloud ID service variables. Includes `id`, `authState`, and `isMCSeed`.
* **`hints`**: [Client hint](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variables. Includes `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`, and `wow64`.
* **`ipaddress`**: The visitor's IP address.
* **`language`**: The [Language](/help/components/dimensions/language.md) dimension.
* **`list1`** - **`list3`**: [List variables](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: The visitor's Experience Cloud ID.
* **`tnta`**: Target data payload used in [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) integrations.
* **`trackingServer`**: The [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variable.
* **`transactionID`**: The [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable.
* **`userAgent`**: The device's user agent string.

The following variables are not supported through Bulk data insertion:

* **`charSet`**: The [`charSet`](/help/implement/vars/config-vars/charset.md) variable. Bulk data insertion only supports UTF-8.
* **`timezone`**: The visitor's time zone offset from GMT in hours.

<!--
clickAction | Object identifier for visitor click map (oid)
clickActionType | Object identifier type for visitor click map (oidt)
clickContext | Page identifier for visitor click map (pid)
clickContextType | Page identifier type for visitor click map (pidt)
clickSourceID | Source index for visitor click map (oi)
clickTag | Object tag name for visitor click map (ot)
scXmlVer | Marketing reports XML request version number (for example, 1.0).
-->
