---
title: Visitor identification using the Web SDK tag extension
description: Correctly identify visitors when implementing the Web SDK tag extension.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
    internal-label: Experience Platform Edge integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Visitor identification using the Web SDK tag extension

The Web SDK tag extension in Adobe Experience Platform Data Collection empowers organizations to implement the Web SDK using a tag management interface. Advanced scenarios like cross-domain ID sharing and visitor profile migration are easily configured through extension rules and actions. Using the Web SDK future-proofs your implementation and supports a seamless upgrade to Customer Journey Analytics.

Identity data can be extended to support custom IDs and multiple namespaces using XDM's [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map). Adobe recommends using ECID as the primary identifier for Analytics, using other identity management options for advanced scenarios.

Since the Visitor ID Service is baked in natively to the tag extension, it only requires that you set **[!UICONTROL Edge Domain]** to the desired value. If this field is set correctly, visitor identification works without any additional configuration.

>[!NOTE]
>
>Do not include the Visitor ID Service tag extension if use the Web SDK tag extension. The Visitor ID Service tag extension is only required if you use the [Adobe Analytics extension](analytics-extension.md).
