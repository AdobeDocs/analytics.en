---
title: Track across different implementation types
description: Use different implementation types and track visitors seamlessly between them.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implmentation Basics
---
# Track across different implementation types

The core architecture of an Adobe Analytics implementation is consistent across all implementation types. The process involves defining variables and compiling them into an image request that is sent to Adobe's data collection servers. This concept means that you can seamlessly switch between AppMeasurement, the Web SDK, and their respective extensions in Adobe Experience Platform Data Collection across different pages of the same site.

Adobe recommends maintaining consistency across a site's implementation by using the same implementation type across all pages. However, if parts of your site have different requirements, you can use this page to help make sure that visitors are consistently tracked between pages.

If you use more than one type of implementation (such as AppMeasurement and hardcoded image requests), make sure that the following variables are correctly set and match each other:

| Variable | AppMeasurement | Analytics extension | Web SDK | Web SDK extension | Hardcoded image request |
| --- | --- | --- | --- | --- | --- |
| Report suite ID | String argument within [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] under the [!UICONTROL Library management] section when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Part of the URL `pathname` (after `/b/ss/`) |
| Tracking Server | The [`trackingServer`](../vars/config-vars/trackingserver.md) and [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variables | [!UICONTROL Tracking Server] and [!UICONTROL SSL Tracking Server] under the [!UICONTROL General] section when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | The `edgeDomain` property when [Configuring the Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) | The [!UICONTROL Edge Domain] when [Configuring the extension](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | The `hostname` of the image request URL |
| Experience Cloud ID service | Implement [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html) | Use the [Adobe Experience Cloud ID Service extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Use the [Adobe Experience Cloud ID Service extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Use the [Adobe Experience Cloud ID Service extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Make a [separate call to the ID Service servers](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) to obtain the desired ID |

{style="table-layout:auto"}

If any of these variables are not consistent across each implementation type, Adobe considers them as separate visitors. If visitors are not seamlessly tracked across implementation types on your site, the most common reason is that the ID Service is configured incorrectly. See [Implementation methods](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) in the ID Service user guide for more information.
