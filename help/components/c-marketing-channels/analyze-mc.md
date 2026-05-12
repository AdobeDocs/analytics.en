---
title: Analyze Marketing Channels
description: Learn how to use Marketing Channels dimensions in Workspace.
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
TQID: https://experienceleague.adobe.com/XWjRuwOusH-TsOb5rzG8rAIkye3faYxfZzyQOMrav3Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Analyze Marketing Channels

>[!NOTE]
>
>To maximize effectiveness of Marketing Channels for Attribution and Adobe Analytics, we have published some [revised best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Analytics administrators can manage marketing channels for their organizations as described in [Manage Marketing Channels](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

You probably want to know which of your marketing channels is the most effective, and with whom, so you can better target your efforts and receive a better return on your marketing dollars. In Adobe Analytics, the Marketing Channels dimensions and metrics in Workspace are one of the tools that can help you track the influence of different channels on your orders, revenue, etc. and give you useful channel insights. Here are the dimensions and metrics you can use related to Marketing Channels:

![](assets/mc-dims.png)

| Dimension/Metric | Definition |
| --- | --- |
| Marketing Channel |This is the recommended Marketing Channels dimension to use. Attribution models can be applied to it at run-time. This dimension behaves identically to Last Touch Channel dimension, but is labeled differently to prevent confusion when using it with a different attribution model.|
| Last Touch Channel | Legacy dimension, with last touch attribution model pre-applied and unchangeable. |
| First Touch Channel | Legacy dimension, with first touch attribution model pre-applied and unchangeable. |
| Marketing Channel Instances | This metric measures the number of times a marketing channel was defined in an image request, including standard page views and custom link calls. Does not include persisted values. |
| New engagements | This metric is similar to Instances, but is only incremented when first-touch marketing channel is defined in an image request. |

## Basic analysis

This Freeform table shows the metrics Online Orders, Online Revenue, and the Conversion Rate for each of the Marketing Channels:

![](assets/mc-viz1.png)

Here you see each Marketing Channel's Online Orders and Online Revenue in a Donut chart:

![](assets/mc-viz2.png)

This Line chart shows trends in Online Orders for various channels over time:

![](assets/mc-viz3.png)

## Advanced analysis

Marketing Channels Details dives more deeply into each channel to show you specific campaigns, placements, etc. You can break down each Marketing Channel into details:

![](assets/mc-viz4.png)

## Apply attribution models

You can use [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) to apply different attribution models instantaneously:

![](assets/mc-viz5.png)

Notice how the same metric (Online Orders) generates different results when you apply different attribution models.

## Cross-tab marketing analysis

Using the legacy First-Touch Channel and Last-Touch Channel, you can get a helpful view into channel interactions:

![](assets/mc-viz6.png)

Learn more about cross-tab marketing analysis in this video: [Using Cross-tab Analysis to Explore Basic Marketing Attribution in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html).
