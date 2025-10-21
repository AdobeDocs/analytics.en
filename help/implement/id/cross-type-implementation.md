---
title: Track across different implementation types
description: Use different implementation types and track visitors seamlessly between them.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
---
# Track across different implementation types

The core architecture of an Adobe Analytics implementation is consistent across all implementation types. The process involves defining variables and compiling them into an image request that is sent to Adobe's data collection servers. This concept means that you can seamlessly switch between AppMeasurement, the Web SDK, and their respective extensions in Adobe Experience Platform Data Collection across different pages of the same site.

Adobe recommends maintaining consistency across a site's implementation by using the same implementation type across all pages. However, if parts of your site have different requirements, you can use this page to help make sure that visitors are consistently tracked between pages.

If you use more than one type of implementation (such as AppMeasurement and hardcoded image requests), make sure that the following variables are correctly set and match each other.

>[!NOTE]
>
>All implementations types must use the same visitor identification type (legacy Analytics ID or Visitor ID Service). Adobe recommends using the Visitor ID Service in all implementations where possible.

| Variable | AppMeasurement | Analytics extension | Web SDK (Alloy) | Web SDK tag extension | Hardcoded image request |
| --- | --- | --- | --- | --- | --- |
| Report suite ID | String argument in [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] under the [!UICONTROL Library management] section when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Part of the URL `pathname` (after `/b/ss/`) |
| Experience Cloud ID service | Implement [`VisitorAPI.js`](appmeasurement.md) | Use the [Experience Cloud ID Service extension](analytics-extension.md) | [Natively included](alloy.md) | [Natively included](web-sdk-extension.md) | Make a [separate call to the ID Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) to obtain the desired ID and include the `mid` in the query string |
| Edge domain | The [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variable | [!UICONTROL SSL Tracking Server] under the [!UICONTROL General] section when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | The `edgeDomain` property when [Configuring the Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) | The [!UICONTROL Edge Domain] field when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | The `hostname` of the image request URL |

If any of these variables are not consistent across each implementation type, Adobe might consider them as separate visitors. If visitors are not seamlessly tracked across implementation types on your site, the most common reason is that the ID Service is configured incorrectly. Ensure that each implementation type correctly obtains the same Experience Cloud ID (`mid`) across your site.
