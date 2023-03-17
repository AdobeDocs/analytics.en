---
title: trackInlineStats
description: Enable or disable Activity map in your implementation.
keywords: disable activity map
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
---
# trackInlineStats

Activity map is a feature in Adobe Analytics that collects data on where visitors click and what they click on. You can view this data in Analytics reports, or by using a browser extension overlay. Enable this variable if you would like to use Activity map features.

When enabled, AppMeasurement collects information about the link and sends that data in the next image request. Information from each click is stored in a cookied labeled `s_sq`.

## Activity Map using the Web SDK

The Web SDK does not yet support Activity Map data collection.

## Enable Clickmap using the Adobe Analytics extension

[!UICONTROL Enable Clickmap] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Enable Clickmap] checkbox.

Click the checkbox to enable Activity map tracking.

## s.trackInlineStats in AppMeasurement and the Analytics extension custom code editor

The `s.trackInlineStats` is a boolean that enables or disables Activity map tracking. Its default value is `false`. Set this value to `true` if you want to enable Activity map data collection.

```js
s.trackInlineStats = true;
```
