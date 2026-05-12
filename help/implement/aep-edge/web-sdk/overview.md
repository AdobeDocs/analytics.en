---
title: Implement Adobe Analytics using the Adobe Experience Platform Web SDK
description: Use the Web SDK to send data to Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/4pS-q3F3W7D1ojdMkCzgUyZkO3LDt1DpFfxqcTtZXLQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
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
---
# Implement Adobe Analytics using the Adobe Experience Platform Web SDK

You can use the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) to send data to Adobe Analytics. There are two main methods to implement the Web SDK, and each method has two implementation types:

| | **Migrate from AppMeasurement** | **Clean Web SDK implementation** |
| --- | --- | --- |
| **Use tags** | [Migrate from the Analytics extension to the Web SDK extension](analytics-extension-to-web-sdk.md) | [Send data to Adobe Analytics using the Web SDK extension](web-sdk-tag-extension.md) |
| **Use JavaScript** | [Migrate from AppMeasurement to the Web SDK JavaScript library](appmeasurement-to-web-sdk.md) | [Send data to Adobe Analytics using the Web SDK JavaScript library](web-sdk-javascript-library.md) |

If your organization requires a new Web SDK implementation and plans to use Customer Journey Analytics in the future, Adobe recommends a clean Web SDK implementation using your own schema. See [Ingest data via the Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) in the Customer Journey Analytics user guide.

## Additional resources

Tags can be highly customized. Learn more about how you can get the most out of Adobe Analytics by including the right data in your implementation.

- [Tags documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): Learn how the interface works and what extensions are available.

- [Adobe Experience Platform Web SDK documentation](https://experienceleague.adobe.com/docs/web-sdk.html)
