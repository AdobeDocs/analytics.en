---
title: trackDownloadLinks
description: Enable or disable automatic link tracking for download links.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
---
# trackDownLoadLinks

Adobe offers the ability to track download links without manually setting the [`tl()`](../functions/tl-method.md) method for each download link. Enable this variable if you would like to use automatic link tracking for download links.

When enabled, AppMeasurement compares any clicked link URL to values in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). If there is a match, a download link tracking call automatically fires.

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

## Track download links using the Adobe Analytics extension

Track download links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Track download links] checkbox.

Click the checkbox to enable automatic download link tracking.

## s.trackDownloadLinks in AppMeasurement and the Analytics extension custom code editor

The `s.trackDownloadLinks` is a boolean that enables or disables automatic download link tracking. If you do not want to track download links, or would prefer to manually call the `tl()` method to track downloads, set this variable to `false`.

```js
s.trackDownloadLinks = true;
```
