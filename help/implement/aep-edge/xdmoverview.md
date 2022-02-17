---
title: Using XDM data with Analytics
description: Overview of using XDM data from Experience Platform in Adobe Analytics
feature: AEP Edge
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
---
# Using Adobe Experience Platform Edge data with Analytics

You can use the [Adobe Experience Platform (AEP) Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) to send data to Adobe Analytics. This works by translating the [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) into a format used by Analytics.

Analytics collects XDM data through two methods:

* Automatic mapping from XDM schemas
* Manual mapping to context data

## Automatic mapping

Automatic mapping relies upon a default [schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) in the XDM that automatically populates JSON objects that are included in typical Analytics data collection. The Analytics variables that are automatically mapped from the XDM to your configured report suites do not require any developer support to incorporate. See [Variables automatically mapped in Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/automatically-mapped-vars.html) in the Platform Web SDK user guide.

## Manual mapping

[Manual mapping of XDM data to Analytics](xdm-manual.md) relies upon [Analytics context data](../vars/page-vars/contextdata.md) variables. These variables are put into JSON objects that correspond to applicable schemas. Typically, your development team adds context data upon implementation and then Admins set [processing rules](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) to apply that data to specified report suites.

## Setup

To set up Analytics to receive XDM data:

1. Install and [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Make sure the applicable report suites are mapped to the data you want. XDM data automatically flows to the report suite from Adobe Experience platform.
