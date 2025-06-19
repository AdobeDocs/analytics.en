---
description: Shows how to build a simple "Page Views per Visits" metric.
title: Build a simple "Page Views per Visits" metric
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
---
# Build a simple calculated metric

The following information explains how to create a simple *Page Views per Visits* metric.

1. Start to build a metric, as described in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Name the metric `Page Views per Visits` or something similar.
1. Give the metric a user-friendly **[!UICONTROL Description]** to show what the metric is used for.
1. Select the right **[!UICONTROL Format]**. For this example, choose **[!UICONTROL Decimal]**.
1. Decide how many decimal places you want the report to show.
1. In the **[!UICONTROL Show updward trend as]** drop-down menu, select **[!UICONTROL Good (Green)]**.
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. For this calculated metric, first drag **[!UICONTROL Page Views]** from the **[!UICONTROL Dimensions]** components into the **[!UICONTROL Definition]** section of the canvas.
1. Then drag **[!UICONTROL Visits]** from the **[!UICONTROL Metrics]** components and drop the metric underneath **[!UICONTROL Page Views]** (wait until the blue line appears before you drop the metric).
1. Select the [!UICONTROL Divide] ![Divide](/help/assets/icons/Divide.svg) operator. (Divide is the default operator.) 
1. You can see a **[!UICONTROL Preview]** of the metric while you are building the metric.
1. [Product compatibility](../../../cm-compatibility.md) shows you whether the metric is compatible with Current Data or only with Fully Processed Data.

   ![Simple calculated metric](assets/simple-calculated-metric.png)
1. Select **[!UICONTROL Save]**.
  
   Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.

1. (Optional) To share, approve, (re-)tag, rename, or delete a metric, you can go to the [Calculated metrics manager](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).
