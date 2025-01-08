---
title: Ad Platform Consent
description: See the configuration for advertising consent for third-party ad providers.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
---
# Ad Platform Consent

The 'Ad Platform Consent' [dimension](overview.md) displays whether consent is collected to send data to third-party advertising providers, like Google, Meta, and others.

Currently, this dimension is used for Google only. Due to European privacy regulations, the Digital Markets Act (DMA), Google is requiring that data sent to their servers and collected in Europe must indicate whether consent is collected. Some Analytics customers send event data via Adobe Advertising as conversion events to Google.

In the future, this dimension can be used to support the encoding of additional consent information for other third-party advertising providers.

## Populate this dimension with data

This dimension collects data from the following [Context data variables](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`
  
You populate the context data variable with relevant values for the Google consent fields

* `ad_user_data` (1st character) and 
* `ad_personalization` (2nd character). 
 
See [Consent in the Google Ads API reference](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) for more information.

The possible values for each of these fields can be:

| Value | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Grant consent to Google for ad user data. | Grant consent to Google for ad personalization. |
| `N` | Deny consent to Google for ad user data. | Denty consent to Google for ad personalization. |
| `U` | Unspecified. | Unspecified. |

The example below grants consent to Google for ad user data but not for ad personalization:

```
contextData.['adConsent'] = "YN..."
```

Characters beyond the first and second character are currently ignored. 

## Use the data

You can use the collected ad consent data:

* Data Feeds: the ad consent data is available using the `dataprivacydmaconsent` [column](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Data Warehouse reports: the ad consent data is available using the **[!UICONTROL Ad Platform Consent]** dimension.

Your organization determines the logic to implement this context data variable. The value does not persist beyond the hit it is set on, so you must set the context data variable on each page.

When you send advertising data from Adobe Analytics via Adobe Advertising as conversion events to Google, please consult the Adobe Advertising team to assist with the integration.

For more information see, [Privacy reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
