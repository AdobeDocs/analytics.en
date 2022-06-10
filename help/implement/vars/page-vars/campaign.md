---
title: campaign
description: Populate the 'Tracking Code' dimension.
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
---
# campaign

The `campaign` variable is dedicated to collecting tracking codes on your site. In previous versions of Adobe Analytics, it had special treatment where it could be used as a breakdown to most dimensions. In the current version of Adobe Analytics, it acts identical to an eVar.

This variable populates the 'Tracking Code' dimension.

## Campaign using the Web SDK

Campaign is [mapped for Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under the XDM field `marketing.trackingCode`.

## Campaign using the Adobe Analytics extension

You can set campaign either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
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
