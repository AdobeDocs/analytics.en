---
title: pageName
description: The name of the page on your site.
feature: Appmeasurement Implementation
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UVcun7asSJzB20Q4TD5EAqt1-M1OY4VUhH--rEJRdc4'
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
# pageName

The `pageName` variable typically stores the name of a given page. It is helpful to determine what individual pages are most popular. This variable populates the [Page](/help/components/dimensions/page.md) dimension.

If this variable is not defined on a given page tracking call, the [`pageURL`](pageurl.md) variable is used instead.

>[!NOTE]
>
>Adobe data collection servers strip this dimension from all [link tracking](/help/implement/vars/functions/tl-method.md) image requests. If you want this dimension to appear in link tracking hits, consider copying this dimension into an [eVar](evar.md).

## Page name using the Web SDK

Page name is mapped to the following variables:

* [XDM object](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.name`
* [Data object](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageName`

## Page name using the Adobe Analytics extension

You can set page name either while configuring the Analytics extension (global variables) or under rules.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click an existing [!UICONTROL Adobe Analytics - Set Variables] action or click the '+' icon.
5. Set the [!UICONTROL Extension] drop-down list to Adobe Analytics, and the [!UICONTROL Action Type] to [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Page name] section.

You can set page name to any string value, including data elements.

## s.pageName in AppMeasurement and the Analytics extension custom code editor

The `s.pageName` variable is a string that typically contains the name of the page. It has a maximum value of 100 bytes; longer values are truncated. This truncation includes instances where it falls back to `pageURL` if this variable is blank.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

If using the `digitalData` [data layer](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
