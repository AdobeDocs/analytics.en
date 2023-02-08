---
title: Classification Sets Overview
description: Use Classification Sets to manage classification data.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
---
# Classification Sets Overview

Classification Sets provide a single interface to manage classifications and rules. This workflow combines the concept of creating classifications in Report Suite Settings with the concept of the Classification Importer to provide a more intuitive interface to create and manage classification data.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

>[!NOTE]
>
>Classification sets will be available to all customers who have their report suites migrated to the new Classifications architecture. Please contact Adobe Customer Care or your Account Manager for more information.

The backend architecture released with Classification Sets contains several notable improvements:

* Significantly reduced processing time (72 hours → 24 hours)
* The ability to use the Classification Sets UI
* The option to use classification data in Adobe Experience Platform in the future through the [Adobe Analytics source connector for classification data](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

The backend architecture released with Classification Sets also contains several notable changes:

* When using the browser import, '[!UICONTROL Overwrite on conflict]' is always enabled.
* When using the browser import, the option to export immediately after import is no longer supported. Exports must be initiated separately.
* The Analytics 2.0 API `GetDimensions` endpoint now returns string identifiers for classifications instead of numeric identifiers. Numeric identifiers can still be used, but Adobe recommends using the new string identifiers where possible. Numeric identifiers can be retrieved by using the `?expansion=hidden` query string parameter.


Classification Sets consist of two main areas:

* [**[!UICONTROL Classification Sets Manager]**](set-manager.md): Create, edit and delete Classification Sets.
* [**[!UICONTROL Classification Set Jobs Manager]**](job-manager.md): View the status of Classification Set Jobs and download export files.
