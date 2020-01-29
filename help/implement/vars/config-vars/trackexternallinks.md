---
title: trackExternalLinks
description: Enable or disable automatic link tracking for exit links.
---

# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the `tl()` function for each exit link. Enable this variable if you would like to use automatic link tracking for exit links.

When enabled, AppMeasurement compares any clicked link URL to values in `linkInternalFilters` and `linkExternalFilters`. If there is a match, an exit link tracking call automatically fires.

## Track outbound links in Adobe Experience Platform Launch

Track outbound links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Track outbound links] checkbox.

Click the checkbox to enable automatic exit link tracking.

## s.trackExternalLinks in AppMeasurement and Launch custom code editor

The `s.trackExternalLinks` is a boolean that enables or disables automatic exit link tracking. If you do not want to track outbound links, or would prefer to manually call the `tl()` function to track exit links, set this variable to `false`.

```js
s.trackDownloadLinks = true;
```
