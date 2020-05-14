---
title: Using XDM data with Analytics
description: Overview of using XDM data from Experience Platform in Adobe Analytics 
---

# Using Adobe Experience Platform Edge data with Analytics


You can use the [Adobe Experience Platform (AEP) Web SDK](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) to send data to Adobe Analytics. This works by translating the [Experience Data Model (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) into a format used by Analytics.

Analytics collects XDM data through two methods:

* Automatic mapping from XDM schemas

* Manual mapping to context data

## Automatic mapping

Automatic mapping relies upon a default [schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) in the XDM that automatically populates JSON objects that are included in typical Analytics data collection. The [Analytics variables that are automatically mapped from the XDM](https://git.corp.adobe.com/analytics-data-collection/anedge/blob/master/XDM_Translator.md) to your configured report suites do not require any developer support to incorporate.

## Manual mapping

Manual mapping of XDM data to Analytics relies upon [Analytics context data](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) variables. These variables are put into JSON objects that correspond to applicable schemas. Typically, your development team adds context data upon implementation and then Admins set [processing rules](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html) to apply that data to specified report suites.


## Setup

To set up Analtyics to receive XDM data:

1. Install and [configure](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) the [Adobe Experience Platform Web SDK](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Make sure the applicable report suites are mapped to the data you want. XDM data automatically flows to the report suite from Adobe Experience platform.

