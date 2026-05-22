---
title: pageURL
description: Override the automatically collected page URL on your site.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
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
# pageURL

AppMeasurement automatically collects the page URL in each hit. If you want to override the page URL automatically collected by AppMeasurement, you can use this variable. You do not need to set this variable in most cases.

>[!NOTE]
>
>This variable is not an available dimension in Analysis Workspace. It is only available in Data Warehouse and Data Feeds. Additionally, Adobe data collection servers strip this dimension from all [link tracking](/help/implement/vars/functions/tl-method.md) image requests. If you want to use page URL as a dimension in Analysis Workspace or want this dimension in link tracking hits, consider passing the `pageURL` variable into an [eVar](evar.md) on every hit.

## Page URL using the Web SDK

Page URL is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` or `data.__adobe.analytics.g`

## Page URL using the Adobe Analytics extension

The Analytics extension in Adobe Experience Platform Data Collection automatically populates page URL. However, you can set the page URL override either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the **[!UICONTROL Rules]** tab, then click the desired rule (or create a rule).
4. Under **[!UICONTROL Actions]**, click an existing **[!UICONTROL Adobe Analytics - Set Variables]** action or click the '+' icon.
5. Set the **[!UICONTROL Extension]** drop-down list to Adobe Analytics, and the **[!UICONTROL Action Type]** to **[!UICONTROL Set Variables]**.
6. Locate the **[!UICONTROL Page URL]** section.

You can set page URL to any string value.

## s.pageURL in AppMeasurement and the Analytics extension custom code editor

The `s.pageURL` variable is a string that contains the URL of the page. AppMeasurement automatically collects this variable, however you can override its value if desired.

```js
s.pageURL = "https://example.com";
```

If you would like to use page URL as a dimension in reports, consider using the following in your implementation:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
