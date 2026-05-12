---
title: Bot name
description: The name of the bot that matched Bot rules.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
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
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Bot name

The 'Bot name' [dimension](overview.md) shows the names of bots that were detected using [Bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). These rules can be default IAB rules, or custom bot rules that your organization configures. It is helpful in cases where you want to learn more about what bots are visiting your site, or which bots generate the most traffic.

Hits that match [!UICONTROL Bot rules] are automatically filtered out of all of Analytics reporting with exception to this dimension, [Bot occurrences](../metrics/bot-occurrences.md), and [Bot page views](../metrics/bot-page-views.md). You can use this dimension and these two metrics to see what bot data is excluded from the rest of your reports.

Since bot reporting is separated from the rest of your report suite data, only the following dimensions and metrics are supported with this dimension:

* [Page](page.md)
* Time-based dimensions (for example, [Day](day.md), [Week](week.md), or [Month](month.md))
* [Bot occurrences](../metrics/bot-occurrences.md)
* [Bot page views](../metrics/bot-page-views.md)

Using any other dimension or metric with this dimension does not return data.

## Populate this dimension with data

If you have enabled [Bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), this dimension automatically collects data. If you have not yet enabled [!UICONTROL Bot rules], this dimension does not appear in Analysis Workspace.

## Dimension items

Each dimension item lists the name of the bot that matched IAB or custom bot rule criteria.
