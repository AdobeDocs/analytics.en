---
title: Track across different implementation types
description: Use different implementation types and track visitors seamlessly between them.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
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
# Track across different implementation types

The core architecture of an Adobe Analytics implementation is consistent across all implementation types. The process involves defining variables and compiling them into an image request that is sent to Adobe's data collection servers. This concept means that you can seamlessly switch between AppMeasurement, the Web SDK, and their respective extensions in Adobe Experience Platform Data Collection across different pages of the same site.

Adobe recommends maintaining consistency across a site's implementation by using the same implementation type across all pages. However, if parts of your site have different requirements, you can use this page to help make sure that visitors are consistently tracked between pages.

If you use more than one type of implementation (such as AppMeasurement and hardcoded image requests), make sure that the following variables are correctly set and match each other.

>[!NOTE]
>
>All implementations types must use the same visitor identification type (legacy Analytics ID or Visitor ID Service). Adobe recommends using the Visitor ID Service in all implementations where possible.

| Variable | Web SDK tag extension | Web SDK (Alloy) | Analytics extension | AppMeasurement | Hardcoded image request |
|---|---|---|---|---|---|
| Report suite ID | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) | Add Adobe Analytics as a service when [Configuring a datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) | [!UICONTROL Report suites] under the [!UICONTROL Library management] section when [Configuring the extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | String argument in [`s_gi`](../vars/functions/s-gi.md) | Part of the URL `pathname` (after `/b/ss/`) |
| Experience Cloud ID service | [Natively included](web-sdk-extension.md) | [Natively included](alloy.md) | Use the [Experience Cloud ID Service extension](analytics-extension.md) | Implement [`VisitorAPI.js`](appmeasurement.md) | Make a [separate call to the ID Service](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) to obtain the desired ID and include the `mid` in the query string |
| Edge domain | The [!UICONTROL Edge Domain] field when [Configuring the extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | The `edgeDomain` property when [Configuring the Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL SSL Tracking Server] under the [!UICONTROL General] section when [Configuring the extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | The [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variable | The `hostname` of the image request URL |

If any of these variables are not consistent across each implementation type, Adobe likely considers them as separate visitors. If visitors are not seamlessly tracked across implementation types on your site, the most common reason is that the ID Service is configured incorrectly. Ensure that each implementation type correctly obtains the same Experience Cloud ID (`mid`) across your site.
