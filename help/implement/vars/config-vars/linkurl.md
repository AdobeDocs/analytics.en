---
title: linkURL
description: Override the automatically generated link URL AppMeasurement uses in link tracking calls.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/O8Bd28njZQDnffeUwCiNGNSNRHk4FU-z48r4pt7Eths'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# linkURL

Whenever a link tracking call is sent to Adobe, AppMeasurement detects the URL that was clicked. This URL helps determine the link type, such as download links and exit links. Use the `linkURL` variable to override the detected URL.

There are no dimensions in Analysis Workspace that report on this variable. It populates the `page_event_var1` column in [Data feeds](/help/export/analytics-data-feed/data-feed-overview.md). If you want to track the URL of a clicked link, Adobe recommends using a custom variable, such as a [Prop](../page-vars/prop.md). The usage of [Activity Map](/help/analyze/activity-map/overview.md) can help streamline the data collection for clicked links.

## Link URL using the Web SDK

Link URL is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` or `data.__adobe.analytics.pev1`

## Link URL using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.linkURL in AppMeasurement and the Analytics extension custom code editor

The `s.linkURL` variable is a string, containing the full URL of the clicked link. This variable does not populate any dimensions available in reporting.

```js
s.linkURL = "https://example.com";
```

If the third argument of the [tl()](../functions/tl-method.md) method is not set, the `linkURL` variable is used instead.
