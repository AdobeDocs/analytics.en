---
title: Getting started with Activity Map
description: Get started using the Activity Map overlay and dimensions.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
TQID: https://experienceleague.adobe.com/Wt30b3LTZWyzAQFOKqkqBdWH2Ifatq5FLp-Z0z7nktA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Getting started with Activity Map

Activity Map in Adobe Analytics comprises four main elements:

* **Report suite setting**: You must enable Activity Map in Report suite settings. When enabled, the report suite creates several reserved variables for Activity Map dimensions and metrics.
* **Implementation**: Collect Activity Map data on your website or property. Customizing how data is collected can improve the quality and experience of reports.
* **Workspace dimensions and metrics**: When your implementation is correctly configured, you can use Activity Map dimensions and metrics in Analysis Workspace.
* **Overlay**: Adobe offers a browser extension to view Activity Map data in the context of your website. This feature is not available for Web SDK implementations.

## Enable report suite setting

A report suite must have Activity Map reporting enabled before you can start collecting data. If your implementation sends Activity Map data to a report suite without Activity Map reporting enabled, Activity Map data is not included in the hit.

**[!UICONTROL Admin]** > **[!UICONTROL Report suites]** > Select report suite > **[!UICONTROL Edit settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map reporting]** > **[!UICONTROL Enable Activity Map Reports]**

Enabling Activity Map reports creates several backend reserved variables. See [Activity Map Reporting](/help/admin/tools/manage-rs/edit-settings/activity-map.md) in the Adobe Analytics admin guide for more information.

## Code installation

Your implementation must be correctly configured to send Activity Map data to Adobe. The overlay browser extension is not available when Adobe Analytics is implemented with the Web SDK.

+++Web SDK tag extension

Activity Map data collection requires the **[!UICONTROL Adobe Experience Platform Web SDK]** extension v2.23 or later. Extension versions down to v2.16 have limited support. These previous extension versions send Activity Map data in a separate event from the rest of your data. This extra event increases the number of hits that you send to Adobe Analytics or Adobe Experience Platform.

The **[!UICONTROL Click data collection]** configuration setting handles Activity Map data collection and is typically enabled by default. You can check to make sure that it is enabled in the extension's configuration settings:

1. Log in to [Adobe CX Enterprise](https://experience.adobe.com) using your Adobe ID credentials.
1. Select **[!UICONTROL Data Collection]** in the quick access menu or the product selector in the top right.
1. Select **[!UICONTROL Tags]** in the left navigation menu.
1. Select the desired tag to edit.
1. Select **[!UICONTROL Extensions]** in the left navigation menu.
1. Select **[!UICONTROL Adobe Experience Platform Web SDK]** in the list of installed extensions, then select **[!UICONTROL Configure]** on the right.
1. Locate the section labeled [!UICONTROL Data Collection] and make sure that the check box **[!UICONTROL Enable click data collection]** is enabled.
1. Select **[!UICONTROL Save]**.
1. If needed, build your changes to a library and publish your changes to production.

See [Configure the Web SDK tag extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) for more information.

+++

+++Web SDK JavaScript library (`alloy.js`)

Activity Map data collection requires the Web SDK JavaScript library v2.20 or later. Library versions down to v2.15 have limited support. These previous library versions send Activity Map data in a separate event from the rest of your data. This extra event increases the number of hits that you send to Adobe Analytics or Adobe Experience Platform.

The Web SDK configuration variable [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) handles the automatic collection of Activity Map data. It is enabled by default unless explicitly disabled.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics tag extension

The **[!UICONTROL Use Activity Map]** configuration setting handles Activity Map data collection and is typically enabled by default. It is available for all tag extensions v1.9.0 or later. You can check to make sure that it is enabled in the extension's configuration settings:

1. Log in to [Adobe CX Enterprise](https://experience.adobe.com) using your Adobe ID credentials.
1. Select **[!UICONTROL Data Collection]** in the quick access menu or the product selector in the top right.
1. Select **[!UICONTROL Tags]** in the left navigation menu.
1. Select the desired tag to edit.
1. Select **[!UICONTROL Extensions]** in the left navigation menu.
1. Select **[!UICONTROL Adobe Analytics]** in the list of installed extensions, then select **[!UICONTROL Configure]** on the right.
1. Make sure that the check box **[!UICONTROL Use Activity Map]** is enabled.
1. Select **[!UICONTROL Save]**.
1. If needed, build your changes to a library and publish your changes to production.

See the [Adobe Analytics extension overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) for more information.

+++

+++Adobe Analytics JavaScript library (`AppMeasurement.js`)

The Activity Map module handles Activity Map data collection, and is included with all AppMeasurement libraries v1.6 or later. You can inspect the `AppMeasurement.js` file to make sure that it is included.

1. Navigate to the [Latest Adobe Analytics AppMeasurement release](https://github.com/adobe/appmeasurement/releases/latest) on GitHub.
1. Download the compressed AppMeasurement library file, then open `AppMeasurement.js` contained inside.
1. The Activity Map module is included near the top of this file. Make sure that this module is included in the AppMeasurement library that your site uses.

+++

## Available dimensions

When Activity Map is enabled for both your report suite and implementation, you can begin using the following dimensions in Analysis Workspace:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md)

## Download and install the browser extension or add-on

In addition to the dimensions available in Analysis Workspace, you can also view Activity Map data as an overlay on your website. To view this overlay, download and install the Activity Map browser extension or add-on.

**[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Download Activity Map]**

This link takes you to your browser's supported extension or add-on marketplace where you can install it. Once installed, the extension or add-on appears in the top right of your browser where you can sign in and enable the overlay.
