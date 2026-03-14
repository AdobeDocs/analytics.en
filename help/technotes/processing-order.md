---
title: Processing order for data in Adobe Analytics
description: Learn the order of components and services that process data in Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
---
# Processing order for data in Adobe Analytics

Adobe offers many ways to alter or manipulate data before it appears in reporting. This page shows the order in which various Adobe Analytics features process data. You can use this list to troubleshoot data inconsistencies, or determine the best feature to use when data adjustments are necessary.

## Data before it is sent to Adobe

Before data is sent to Adobe, it is typically compiled client-side using one of the following methods:

* **AppMeasurement**: A JavaScript file hosted on your site and referenced on each page. Data is sent directly to Adobe Analytics.
* **Adobe Experience Platform Web SDK**: A JavaScript file hosted on your site and referenced on each page. Data is sent to the Adobe Experience Platform Edge Network.
* **Tags in Adobe Experience Platform Data Collection**: A JavaScript file referenced on each page, containing rules created within the Data Collection UI. The Adobe Analytics extension offers an easier way to implement AppMeasurement. The Web SDK extension offers an easier way to implement the Web SDK.
* **API**: Both AppMeasurement and the Edge Network offer programmatic methods to send data to Adobe. AppMeasurement offers the [Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) and the [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/); the Edge Network offers the [Data collection API](https://developer.adobe.com/data-collection-apis/docs/).

If you send data to the Edge Network, you can configure it to forward data to Adobe Analytics (as well as many other Adobe Experience Cloud solutions). Regardless of implementation method, the collected hit data ultimately arrives to Adobe Analytics processing servers in a format that it can parse.

## Pre-processing in Adobe Analytics collection (pre-processing)

Once data arrives to Adobe Analytics, it enters a pre-processing phase:

1. [**Dynamic variables**](/help/implement/vars/page-vars/dynamic-variables.md): If a dynamic variable is seen in any part of an image request, the value is copied over and treated as an independent value moving forward.
1. [**IP obfuscation (last octet)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): If your report suite is configured to obfuscate only the last octet, that obfuscation applies here. Note that IP obfuscation (remove IP) happens later in the processing pipeline.
1. **Lookup tables**: Dimensions that rely on Adobe-internal lookup tables (for example, the [Browser](/help/components/dimensions/browser.md) dimension) are matched to its corresponding value.
1. [**IP exclusion**](/help/admin/tools/exclude-ip.md): Any IP addresses that you explicitly exclude from reporting are flagged during this step.
1. [**Bot rules**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): Apply standard or custom bot filtering to exclude that data from reporting.
1. **Geolocation data**: Dimensions that rely on IP address lookup (for example, the [Countries](/help/components/dimensions/countries.md) dimension) are populated.
1. [**Processing rules**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): Custom rules applied to your data by your organization. Includes the mapping of [Context data variables](/help/implement/vars/page-vars/contextdata.md) to their respective Analytics variables.
1. [**VISTA rules**](vista.md): Custom flexible rules applied to your data by an Adobe consultant. VISTA rules can potentially run before or after Processing rules, depending on your organization's needs. Most VISTA rules generally run after Processing rules, but each organization is set up differently. Contact your Adobe Account Team for more information about existing VISTA rules.
1. **Currency conversion**: If the hit contains a different [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) than the report suite's currency, any applicable currency variables are converted using the current day's exchange rate.
1. [**Zip code**](/help/components/dimensions/zip-code.md): The 'Zip code' dimension is populated based on report suite settings.

## "Mid-value" stage of the data collection pipeline

When hit-level processing is finished, several features use this partially processed form of data (known as "mid-values"). Before that data is sent anywhere, some mid-value-specific processing is applied:

1. [**Hit-level marketing channel processing rules**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): These processing rules are specifically run for the Analytics Source Connector. Since there is no visit or visitor level context yet, these processing rules assume that a hit is not the first hit of a visit. The results of running the processing rules for a hit are available in `channel.typeAtSource` and `channel._id`.
1. [**IP obfuscation (remove IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): If your report suite is configured to completely obfuscate an IP address, that obfuscation applies here (only for mid-values).

At this point, mid-value data is sent to its respective feature:

* [**Livestream API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/): Connect an application to Adobe's livestream service for a flow of data as it is collected.
* [**Analytics Source Connector**](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics): Ingest Adobe Analytics report suite data in an Adobe Experience Platform dataset.
* [**Real-time reporting**](/help/components/c-real-time-reporting/realtime.md): Provides up to three configurable real-time reports in Analysis Workspace.

## Visit and visitor-level processing

Up to this point, a given hit has no knowledge or context of hits that were collected before or after it. This stage of processing populates visit and visitor level fields.

1. [**Visit + visitor definition**](/help/implement/id/overview.md): The hit is identified based on its contained visitor variables.
1. [**Visit number**](/help/components/dimensions/visit-number.md): Based on other visits for the identified visitor, the visit number is calculated.
1. [**Event deduplication**](/help/implement/vars/page-vars/purchaseid.md): If the hit contains a duplicate purchase ID or event serialization, those IDs are checked and respectively flagged.
1. [**Visit-level marketing channel processing rules**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): Every hit runs through marketing channel processing rules, and its channel + channel detail are determined if the hit matches any rule. These rules populate the [Marketing channel](/help/components/dimensions/marketing-channel.md) and [Marketing channel detail](/help/components/dimensions/marketing-detail.md) dimensions available in Analysis Workspace.
1. **Variable persistence**: For dimensions that have persistence (such as [eVars](/help/components/dimensions/evar.md)), that value is determined at this step.
1. **Transaction ID snapshot**: If the hit contains a [`transactionID`](/help/implement/vars/page-vars/transactionid.md) value, a "snapshot" of all supported values is stored. When a data source upload contains a matching transaction ID, all supported values are included in that data source row.
1. [**IP obfuscation (remove IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): If your report suite is configured to completely obfuscate an IP address, that obfuscation applies here after all other processing finishes.

At this point, the individual hit is recorded in report suite data tables. After the standard [latency](latency.md) interval, it is available in reporting.

## Changing data after it is processed

Data in Adobe Analytics is mostly permanent; however, there are some features that can allow selective data adjustment or removal:

* [**Data repair API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Edit certain columns or delete desired rows of data.
* [**Data governance**](/help/technotes/privacy/privacy-overview.md): Accommodate privacy requests to permanently delete data.
* [**Classifications**](/help/components/classifications/classifications-overview.md): Create dimensions based on rules or uploaded data that allows you to organize data differently. The underlying report suite data is not changed, so you can freely edit or overwrite classification data.
* [**Virtual report suites**](/help/components/vrs/vrs-about.md): Create an alternate report suite view that can change the visit timeout.
