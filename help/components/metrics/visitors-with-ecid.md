---
title: Visitors with Experience Cloud ID
description: The number of unique visitors using an ECID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
    internal-label: CX Enterprise integration
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Visitors with Experience Cloud ID

The '[!UICONTROL Visitors with Experience Cloud ID]' [metric](overview.md) shows the number of unique visitors who were identified by Adobe with an ECID (using the [Visitor ID Service](https://experienceleague.adobe.com/en/docs/id-service/using/home) or [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home)). This metric is helpful to compare with the [Unique visitors](unique-visitors.md) metric to make sure the majority of visitors to your site uses an ECID. If a large portion of visitors don't use this identifier, it can indicate an issue within your implementation.

>[!NOTE]
>
>This metric is especially important for debugging if you use multiple CX Enterprise services, such as Adobe Target or Adobe Audience Manager. Segments shared across CX Enterprise products do not include visitors without an ECID.

## How this metric is calculated

This metric is based on the [Unique visitors](unique-visitors.md) metric, except it only includes individuals identified using the `mid` query string (based on the [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie).

## Debug your ECID setup

The '[!UICONTROL Visitors with Experience Cloud ID]' metric can be useful in troubleshooting CX Enterprise integrations, or identifying areas of your site that don't have the Visitor ID Service or Experience Platform Identity Service deployed.

Drag the '[!UICONTROL Visitors with Experience Cloud ID]' side-by-side with Unique visitors to compare them:

![Unique visitor comparison](assets/metric-mcvid1.png)

In this example, notice that each page has the same number of '[!UICONTROL Unique Visitors]' as '[!UICONTROL Visitors with Experience Cloud ID]'. However, the total number of '[!UICONTROL Unique Visitors]' is greater than the total number of '[!UICONTROL Visitors with Experience Cloud ID]'. You can create a [calculated metric](../calculated-metrics/cm-overview.md) to find out which pages are not using an ECID using the following definition:

![Calculated metric definition](assets/metric-mcvid2.png)

By adding the calculated metric to the report, you can sort the Pages report so that the pages with the highest number of visitors without an ECID are surfaced:

![Pages without ECID](assets/metric-mcvid3.png)

Note that the "Product Quick Views" dimension item are not properly implemented with an ECID. You can work with appropriate teams within your organization to update these pages as soon as possible. You can construct a similar report with any type of dimension such as [Browser type](../dimensions/browser-type.md), [Site section](../dimensions/site-section.md), or any [eVar](../dimensions/evar.md).
