---
title: Mobile lifecycle dimensions
description: Dimensions based on data collected using the Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Mobile lifecycle dimensions

>[!BEGINSHADEBOX]

*This page references data tracked commonly through the Adobe Experience Platform Mobile SDK. For mobile device information using user agent, see [Mobile lookup dimensions](mobile-dimensions.md). For metrics tracked using the Mobile SDK, see [Mobile lifecycle metrics](../metrics/lifecycle-metrics.md).*

>[!ENDSHADEBOX]

| Lifecycle dimension name | Description | Context data variable |
| --- | --- | --- |
| **[!UICONTROL First Launch Date]** | The date that the app was first run after it was installed or reinstalled, in `M/d/yyyy` format. | `a.InstallDate` |
| **[!UICONTROL Device Name (SDK)]** | The device name that the SDK collects. | `a.DeviceName` |
| **[!UICONTROL Operating System Version (SDK)]** | The operating system name and version that the SDK collects. | `a.OSVersion` |
| **[!UICONTROL Resolution (SDK)]** | The device's screen resolution in pixels, as width x height. | `a.Resolution` |
| **[!UICONTROL Acquisition Source]** | The original referrer for an app acquisition campaign, such as a newsletter or a social media network. | `a.referrer.campaign.source` |
| **[!UICONTROL App Id]** | The app name and version, in the format `AppName BundleVersion (app version code)`. For example, `MyAppName 1.1(1)`. | `a.AppID` |
| **[!UICONTROL Acquisition Medium]** | The marketing medium for an app acquisition campaign, such as a banner or email. | `a.referrer.campaign.medium` |
| **[!UICONTROL Acquisition Term]** | Paid keywords or other terms associated with an app acquisition campaign. | `a.referrer.campaign.term` |
| **[!UICONTROL Acquisition Content]** | The name or ID of the content that displayed the app acquisition link. | `a.referrer.campaign.content` |
| **[!UICONTROL Acquisition Name]** | The name of the app acquisition campaign. | `a.referrer.campaign.name` |
| **[!UICONTROL Location (down to 10 km)]** | The visitor's latitude and longitude, accurate to the first decimal place. For example, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL Location (down to 100 m)]** | The visitor's latitude and longitude, accurate to the third decimal place. For example, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL Location (down to 1 m)]** | The visitor's latitude and longitude, accurate to the fifth decimal place. For example, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL Point of Interest Name]** | The name of the point of interest (POI) that the device is in. When you use the [Places extension](https://developer.adobe.com/client-sdks/solution/places/), this value is the Places region name. | `a.loc.poi` |
| **[!UICONTROL Distance to Point of Interest Center]** | The distance between the device and the center of the point of interest that the device is in. | `a.loc.dist` |
| **[!UICONTROL Launch Number]** | The number of times the app was launched or brought out of the background. | `a.Launches` |
| **[!UICONTROL Days Since First Use]** | The number of days since the app was first run. | `a.DaysSinceFirstUse` |
| **[!UICONTROL Action Name]** | The name of the action sent in a `trackAction` call. | `a.action` |
| **[!UICONTROL Lifetime Value (evar)]** | The lifetime value of a user, such as lifetime purchases, ad views, video completes, or social shares. | `a.ltv.amount` |
| **[!UICONTROL Beacon Major]** | The major ID of the beacon that the device is near. | `a.beacon.major` |
| **[!UICONTROL Beacon Minor]** | The minor ID of the beacon that the device is near. | `a.beacon.minor` |
| **[!UICONTROL Beacon UUID]** | The UUID of the beacon that the device is near. | `a.beacon.uuid` |
| **[!UICONTROL Beacon Proximity]** | The device's proximity to the beacon: `0` (unknown), `1` (immediate), `2` (near), or `3` (far). | `a.beacon.prox` |
| **[!UICONTROL Days Since Last Use]** | The number of days since the app was last used. | `a.DaysSinceLastUse` |
| **[!UICONTROL Hour of Day (SDK)]** | The hour that the app was launched, in 24-hour format. Useful for time parting to determine peak usage times. | `a.HourOfDay` |
| **[!UICONTROL Day of Week (SDK)]** | The day of the week that the app was launched. | `a.DayOfWeek` |
| **[!UICONTROL Point of Interest ID]** | The ID of the point of interest that the device is in. When you use the [Places extension](https://developer.adobe.com/client-sdks/solution/places/), this value is the Places region ID. | `a.loc.poi.id` |

>[!NOTE]
>
>Some of these dimensions are populated by methods in the legacy Mobile Services SDK (4.x), which is no longer supported. The Adobe Experience Platform Mobile SDK does not populate them automatically:
>
>* **Acquisition dimensions** ([!UICONTROL Acquisition Source], [!UICONTROL Medium], [!UICONTROL Term], [!UICONTROL Content], and [!UICONTROL Name]): Populated by Mobile App Acquisition, which the Mobile SDK [does not support](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/).
>* **[!UICONTROL Location] dimensions and [!UICONTROL Distance to Point of Interest Center]**: Populated by the 4.x `trackLocation` method. The Mobile SDK replaces this method with the [Places extension](https://developer.adobe.com/client-sdks/solution/places/), which populates [!UICONTROL Point of Interest Name] and [!UICONTROL Point of Interest ID].
>* **[!UICONTROL Lifetime Value (evar)]**: Populated by the 4.x `trackLifetimeValueIncrease` method.
>* **Beacon dimensions** ([!UICONTROL Beacon Major], [!UICONTROL Minor], [!UICONTROL UUID], and [!UICONTROL Proximity]): Populated by the 4.x `trackBeacon` method. To send beacon data with the Mobile SDK, see [Tracking beacons](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/).
>
>See [Adobe Mobile Library (v4) to Experience Platform Analytics migration](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) for more information.
