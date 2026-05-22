---
title: trackDownloadLinks
description: Enable or disable automatic link tracking for download links.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mH9olBbVVqz9WCBCWiZuDe9JcljL0ADOesKSfEE6gkA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
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
# trackDownloadLinks

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

The `s.trackDownloadLinks` is a boolean that enables or disables automatic download link tracking. If you do not want to track download links, or would prefer to manually call the `tl()` method to track downloads, set this variable to `false`. The variable [linkDownloadFileTypes](linkdownloadfiletypes.md) must also be set for automatic download link tracking to work.

```js
s.trackDownloadLinks = true;
```
