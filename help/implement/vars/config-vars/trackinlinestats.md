---
title: trackInlineStats
description: Enable or disable Activity map in your implementation.
---

# trackInlineStats

Activity map is a feature in Adobe Analytics that collects data on where visitors click and what they click on. You can view this data in Analytics reports, or by using a browser extension overlay. Enable this variable if you would like to use Activity map features.

When enabled, AppMeasurement collects information about the link and sends that data in the next image request. Information from each click is stored in a cookied labeled `s_sq`.

## Enable Clickmap in Adobe Experience Platform Launch

[!UICONTROL Enable Clickmap] is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Enable Clickmap] checkbox.

Click the checkbox to enable Activity map tracking.

## s.trackInlineStats in AppMeasurement and Launch custom code editor

The `s.trackInlineStats` is a boolean that enables or disables Activity map tracking. Its default value is `false`. Set this value to `true` if you want to enable Activity map data collection.

```js
s.trackInlineStats = true;
```
