---
title: campaign
description: Populate the 'Tracking Code' dimension.
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/4OF7xoZs8bLS4UW8wfJYHqSyc-gNVLAfPs5j3NwZCcM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# campaign

The `campaign` variable is dedicated to collecting tracking codes on your site. In previous versions of Adobe Analytics, it had special treatment where it could be used as a breakdown to most dimensions. In the current version of Adobe Analytics, it acts identical to an eVar.

This variable populates the [Tracking Code](/help/components/dimensions/tracking-code.md) dimension. It typically gets its value from a query string using the [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) utility method. However, your organization determines exactly how to set this variable.

## Campaign using the Web SDK

Campaign is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` or `data.__adobe.analytics.v0`

## Campaign using the Adobe Analytics extension

You can set campaign either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Campaign] section.

You can set campaign to a value or a query string parameter.

## s.campaign in AppMeasurement and the Analytics extension custom code editor

The `s.campaign` variable is a string that typically contains a tracking code used in marketing efforts. Its max length is 255 bytes; values longer than 255 bytes are automatically truncated when sent to Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
