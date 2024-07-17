---
title: Getting started with Activity Map
description: Get started using the Activity Map overlay and dimensions.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
---
# Getting started with Activity Map

Activity Map in Adobe Analytics comprises four main elements:

* **Report suite setting**: You must enable Activity Map in Report suite settings. When enabled, the report suite creates several reserved variables for Activity Map dimensions and metrics.
* **Implementation**: Collect Activity Map data on your website or property. Customizing how data is collected can improve the quality and experience of reports.
* **Workspace dimensions and metrics**: When your implementation is correctly configured, you can use Activity Map dimensions and metrics in Analysis Workspace.
* **Overlay**: Adobe offers a browser extension to view Activity Map data in the context of your website.

## Enable report suite setting

A report suite must have Activity Map reporting enabled before you can start collecting data. If your implementation sends Activity Map data to a report suite without Activity Map reporting enabled, Activity Map data is not included in the hit.

**[!UICONTROL Admin]** > **[!UICONTROL Report suites]** > Select report suite > **[!UICONTROL Edit settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map reporting]** > **[!UICONTROL Enable Activity Map Reports]**

Enabling Activity Map reports creates several backend reserved variables. See [Activity Map Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) in the Adobe Analytics admin guide for more information.

## Code installation

Your implementation must be correctly configured to send Activity Map data to Adobe.

+++Web SDK tag extension

Activity Map data collection requires the **[!UICONTROL Adobe Experience Platform Web SDK]** extension v2.23 or later. Extension versions down to v2.16 have limited support. These previous extension versions send Activity Map data in a separate event from the rest of your data. This extra event increases the number of hits that you send to Adobe Analytics or Adobe Experience Platform.

The **[!UICONTROL Click data collection]** configuration setting handles Activity Map data collection and is typically enabled by default. You can check to make sure that it is enabled in the extension's configuration settings:

1. Log in to [experience.adobe.com](https://experience.adobe.com)
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
  "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
  "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg",
  "clickCollectionEnabled": true
});
```

+++

+++Adobe Analytics tag extension

The **[!UICONTROL Use Activity Map]** configuration setting handles Activity Map data collection and is typically enabled by default. It is available for all tag extensions v1.9.0 or later. You can check to make sure that it is enabled in the extension's configuration settings:

1. Log in to [experience.adobe.com](https://experience.adobe.com)
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
