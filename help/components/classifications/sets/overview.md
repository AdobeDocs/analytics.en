---
title: Classification sets overview
description: Use classification sets to manage classification data.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
---
# Classification sets overview

Classification sets provide a single interface to manage classifications and rules. This workflow combines the concept of creating classifications in Report suite settings with the concept of the Classification importer to provide a more intuitive interface to create and manage classification data.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

The backend architecture released with Classification sets contain several notable improvements:

* Significantly reduced processing time (72 hours → 24 hours)
* The ability to use the Classification sets UI
* The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

The backend architecture released with Classification sets also contain several notable changes:

* When using the browser or automated import, '[!UICONTROL Overwrite on conflict]' is always enabled.
* When using the browser or automated import, the option to export immediately after import is no longer supported. Exports must be initiated separately.
* The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.

>[!IMPORTANT]
>
>The performance of classification sets mainly depend on the number of unique key values that contain data. Adobe recommends exercising care when dealing with variables that contain large numbers of unique values. This caution especially applies when combining variables from multiple report suites and dimensions into a single classification set.

Classification sets consist of three main areas:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): Create, edit and delete classification sets.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): View the status of classification set jobs and download export files.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): Combine multiple classification sets into a single classification set.
