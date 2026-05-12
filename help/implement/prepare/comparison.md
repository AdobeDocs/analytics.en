---
title: Compare implementation methods
description: See the advantages of each method sending data to Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Tx3YIRJv4Qztv-Bsa9XJFMFVE0PW9SnvgrYeMmrULiA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
# Compare implementation methods

See how each method of implementing Adobe Analytics compares to each other. You can use these tables to help your organization determine the most ideal way to send data to Adobe. Click on each column for more specific information.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Adobe Analytics extension](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Web SDK extension](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Implementation requirements | Reference `AppMeasurement.js` on each page, define variables, send data using `s.t()` to Adobe Analytics | Reference tag loader on each page, use the Data Collection UI to define variables and send data to Adobe Analytics | Reference `Alloy.js` on each page, use `alloy("sendEvent",{})` to compose XDM objects and send the desired data using Edge Network to Adobe Analytics | Reference tag loader on each page, use the Data Collection UI to compose XDM objects and send the desired data using Edge Network to Adobe Analytics |
| Data destination | Sent directly to Adobe Analytics | Sent directly to Adobe Analytics | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics |
| Difficulty making implementation adjustments | Requires access to website code for every implementation change | Change the website code once to install the loader tag; all further implementation updates can be made in the Data Collection UI | Requires access to website code for every implementation change | Change the website code once to install the loader tag; all further implementation updates can be made in the Data Collection UI |
| How A4T is handled | A4T calls are included in hits sent to Adobe | A4T calls are included in hits sent to Adobe | A4T calls are sent as separate hits | A4T calls are sent as separate hits |
| Context Data | Use `s.contextData`. | Use `s.contextData` in custom code blocks | All unmapped fields are automatically sent as `a.x.*` context data variables. | All unmapped fields are automatically sent as `a.x.*` context data variables. |

{style="table-layout:auto"}

## Mobile and Others

>[!CAUTION]
>
>Support for Version 4 Mobile SDKs ended on August 31, 2021. See [Adobe Mobile Services end-of-life FAQ](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) for more information.


| | [Mobile SDK](/help/implement/aep-edge/mobile-sdk/overview.md)| [Edge Network API](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| Implementation requirements | Reference tag loader in the app, then use direct API calls or rules in Data Collection UI to compose XDM objects and send the desired data using Edge Network to Adobe Analytics | Use the Edge Network API to compose XDM objects and send the desired data using Edge Network to Adobe Analytics |
| Data destination | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics | Sent to Adobe Experience Platform Edge, which forwards data to Adobe Analytics |
| Difficulty making implementation adjustments | Change the app code where direct API calls are made or make changes in the Data Collection UI | Requires access to app code for every implementation change |
| How A4T is handled | A4T calls are sent as separate hits | A4T calls are sent as separate hits |
| Context Data | All unmapped fields are automatically sent as `a.x.*` context data variables. | All unmapped fields are automatically sent as `a.x.*` context data variables |

{style="table-layout:auto"}
