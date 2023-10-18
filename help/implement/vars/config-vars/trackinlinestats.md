---
title: trackInlineStats
description: Enable or disable ClickMap in your implementation.
keywords: disable clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
---
# trackInlineStats

>[!IMPORTANT]
>
>This variable is retired. See [Enable Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) instead.

Clickmap is a retired feature in Adobe Analytics that collects data on where visitors click and what they click on. The feature was retired and replaced with [Activity Map](/help/analyze/activity-map/activity-map.md).

When enabled, AppMeasurement collects information about the link and sends that data in the next image request. Information from each click is stored in a cookied labeled `s_sq`.

## Enable Clickmap using the Adobe Analytics extension

[!UICONTROL Enable Clickmap] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Enable Clickmap] checkbox.

## s.trackInlineStats in AppMeasurement and the Analytics extension custom code editor

The `s.trackInlineStats` is a boolean that enables or disables ClickMap tracking. Since the feature is retired, Adobe does not recommend setting this variable. Its default value is `false`.

```js
s.trackInlineStats = false;
```
