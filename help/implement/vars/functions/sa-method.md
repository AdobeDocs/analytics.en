---
title: sa
description: Change the report suite at any time in your implementation.
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/xA02rmiZkiSsFwmACdN-YUlwKVGgeprnySEKEO0w3l8'
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
# sa

The `sa()` method lets you dynamically change a report suite at any time on the page. If you want to send data to different report suites without a page reload, you can use this method.

## Handling report suites using the Web SDK

The Web SDK operates by sending data to a specific Datastream, which forwards data to the desired Analytics Report Suite(s). A single Datastream can forward data to multiple Report Suites. This section applies to both the Web SDK extension and manually implementing the Web SDK.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL Datastreams]** on the left.
1. Click the desired Datastream, or click **[!UICONTROL New Datastream]**.
1. Click **[!UICONTROL Add Service]**, then select **[!UICONTROL Adobe Analytics]**.
1. Enter the desired Report Suite ID. If you want to send the same data to multiple report suites, click **[!UICONTROL Add Report Suite]**.
1. Once all desired report suites are entered, click **[!UICONTROL Save]**.

## Set the desired Datastream using the Web SDK extension

The Web SDK extension provides a Datastream drop-down list for each environment. Alternatively, you can manually enter the Datastream ID.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Datastreams], choose the desired Datastream in the drop-down list for each environment.
1. Click **[!UICONTROL Save]**.

## Set the desired Datastream manually implementing the Web SDK

Set the `datastreamId` configuration variable to the Datastream ID. The Datastream ID is found on the right when viewing a Datastream in Adobe Experience Platform Data Collection.

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

See [Configure the Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) in the Web SDK documentation for more information.

## Change report suite using the Adobe Analytics extension

There is not a flexible way to change report suite in the interface. You can set report suite under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension. However, you cannot change or update the report suite using rules. If you want to update report suite values after they are set, use the custom code editor following AppMeasurement syntax.

## s.sa() in AppMeasurement and the Analytics extension custom code editor

Call the `s.sa()` method to change the destination report suite. Its only argument is a string containing a report suite ID, or multiple report suite IDs delimited by a comma. The report suite ID argument is required. Do not use spaces in the string argument.

```js
s.sa("examplersid");
```

For example, you can change the report suite if the user takes a specific action on your site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
