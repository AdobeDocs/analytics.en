---
title: linkURL
description: Override the automatically generated link URL AppMeasurement uses in link tracking calls.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
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
