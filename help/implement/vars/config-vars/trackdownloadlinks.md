---
title: trackDownloadLinks
description: Enable or disable automatic link tracking for download links.
---

# trackDownLoadLinks

Adobe offers the ability to track download links without manually setting the [`tl()`](../functions/tl-method.md) method for each download link. Enable this variable if you would like to use automatic link tracking for download links.

When enabled, AppMeasurement compares any clicked link URL to values in [`linkDownloadFileTypes`](linkdownloadfiletypes.md). If there is a match, a download link tracking call automatically fires.

## Track download links in Adobe Experience Platform Launch

Track download links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Track download links] checkbox.

Click the checkbox to enable automatic download link tracking.

## s.trackDownloadLinks in AppMeasurement and Launch custom code editor

The `s.trackDownloadLinks` is a boolean that enables or disables automatic download link tracking. If you do not want to track download links, or would prefer to manually call the `tl()` method to track downloads, set this variable to `false`.

```js
s.trackDownloadLinks = true;
```
