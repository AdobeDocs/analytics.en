---
title: trackInlineStats
description: (Retired) Enable or disable ClickMap in your implementation.
keywords: disable clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UoeOR4qNKfuectzZJVKJ2gCNhSxMSBOggMEj9Z9v08g'
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
# trackInlineStats

>[!IMPORTANT]
>
>This variable is retired and no longer used.

ClickMap is a retired feature in Adobe Analytics that collects data on where visitors click and what they click. The feature was replaced with [Activity Map](/help/analyze/activity-map/overview.md).

When enabled, AppMeasurement collects information about the link and sends that data in the next image request. Information from each click is stored in a cookie labeled `s_sq`.

## Enable ClickMap using the Adobe Analytics extension

[!UICONTROL Enable ClickMap] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Enable ClickMap] checkbox.

>[!NOTE]
>
>This checkbox is different from the [!UICONTROL Use Activity Map] checkbox, which is under the [!UICONTROL Library management] accordion.

## s.trackInlineStats in AppMeasurement and the Analytics extension custom code editor

The `s.trackInlineStats` is a boolean that enables or disables ClickMap tracking. Since the feature is retired, Adobe does not recommend setting this variable. Its default value is `false`.

```js
s.trackInlineStats = false;
```
