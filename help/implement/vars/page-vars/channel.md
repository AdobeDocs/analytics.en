---
title: channel
description: Populate the 'Site Sections' dimension.
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/8O57DR-hVZaTuPvVFeOabX-OO6t-Ym7XCKogurcI810'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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
# channel

The `channel` variable typically stores the section of the site a given page is on. It is helpful to determine what groups of your site are most popular. This variable populates the 'Site Sections' dimension.

## Channel using the Web SDK

Channel is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` or `data.__adobe.analytics.ch`

## Channel using the Adobe Analytics extension

You can set channel either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Channel] section.

You can set channel to any string value or data element.

## s.channel in AppMeasurement and the Analytics extension custom code editor

The `s.channel` variable is a string that typically contains the page's site section. It has a maximum value of 100 bytes; longer values are truncated.

```js
s.channel = "Example site section";
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
