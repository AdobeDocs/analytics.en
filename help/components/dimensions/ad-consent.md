---
title: Ad Platform Consent
description: See the configuration for advertising consent for third-party ad providers.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
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

For more information see, [Privacy reporting](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md).
