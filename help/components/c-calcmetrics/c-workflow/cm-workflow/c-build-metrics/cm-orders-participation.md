---
description: Explains how to create a metric that shows which Marketing Channels assist in driving orders. This can be adapted to any dimension or success event of interest.
title: Order Assists metric
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
---
# Build an "Order Assists" metric

The following information explains how to create a metric that shows which Marketing Channels assist in driving orders. This can be adapted to any dimension or success event of interest. 

1. Begin creating a calculated metric, as described in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. In the Calculated metrics builder, name the metric "Assisted Orders".

1. In the Definition canvas, drag in an Orders metric. Then, adjust the attribution model through the settings gear by checking the **[!UICONTROL Use non-default attribution models]** checkbox.

   ![](assets/attr-model.png)

1. Select **[!UICONTROL Custom]** as the attribution model. Change the weights to 0 (starter), 100 (player), and 0 (closer).

   ![](assets/custom-attr-model.png)

1. Select [!UICONTROL **Apply**] > [!UICONTROL **Save**].

1. In Analysis Workspace, create a freeform table with the Marketing Channel dimension, Orders, and your new Assisted Orders metric.

   ![](assets/mktg-channel-assists.png)

   This is an easy way to tell which Marketing Channels assisted in driving orders. Alternatively, from a freeform table, you can right-click any metric and adjust the attribution model directly from the table.

1. (Optional) Share the metric with other users in your organization, as described in [Share calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
