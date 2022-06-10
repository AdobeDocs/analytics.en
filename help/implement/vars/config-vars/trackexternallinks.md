---
title: trackExternalLinks
description: Enable or disable automatic link tracking for exit links.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
---
# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. Enable this variable if you would like to use automatic link tracking for exit links.

When enabled, AppMeasurement compares any clicked link URL to values in [`linkInternalFilters`](linkinternalfilters.md) and [`linkExternalFilters`](linkexternalfilters.md). If there is a match, an exit link tracking call automatically fires.

## Enable or disable click collection using the Web SDK extension

Use the [!UICONTROL Enable click data collection] checkbox when configuring the Web SDK. This checkbox handles both exit and download links.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection], click the **[!UICONTROL Enable click data collection]** checkbox.

## Enable or disable click collection manually implementing the Web SDK

Configure the SDK using [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). The field is a boolean that determines if data associated with link clicks are automatically collected. Its default value is `true`. Set this value to `false` if you want to disable automatic link tracking. This setting handles automatic link tracking for both download and exit links.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Track outbound links using the Adobe Analytics extension

Track outbound links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Track outbound links] checkbox.

Click the checkbox to enable automatic exit link tracking.

## s.trackExternalLinks in AppMeasurement and the Analytics extension custom code editor

The `s.trackExternalLinks` is a boolean that enables or disables automatic exit link tracking. If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
