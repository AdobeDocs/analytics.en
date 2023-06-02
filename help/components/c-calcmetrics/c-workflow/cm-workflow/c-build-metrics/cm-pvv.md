---
description: Shows how to build a simple "Page Views per Visits" metric.
title: Build a simple "Page Views per Visits" metric
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
---
# Build a "Page Views per Visits" metric

The following information explains how to create a simple "Page Views per Visits" metric.

To build a simple "Page Views per Visits" metric:

1. Begin building a metric, as described in [Build metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
1. Name the metric ""Page Views per Visits" or something similar.
1. Give it a user-friendly **[!UICONTROL Description]** to show what it's used for.
1. Select the right **[!UICONTROL Format]**. For this example, choose [!UICONTROL **Decimal**].
1. Decide how many decimal places you want the report to show.
1. In the [!UICONTROL **Show updward trend as**] drop-down menu, select [!UICONTROL **Good (Green)**].
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. For this metric, first drag Page Views into the [!UICONTROL **Definition**] section of the canvas, then drag Visits beneath it (wait until the blue line appears before you drop it).
1. Select the Divide operator. (Divide is the default operator.) 
1. You can now see a **[!UICONTROL Preview]** of that metric as you are building it, at the top right.
1. Product compatibility shows you whether the metric is compatible with [Current Data](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) or only with Fully Processed Data.
1. Select **[!UICONTROL Save]**.
  
   Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.

1. (Optional) To share, approve, (re-)tag, rename, or delete a metric, you can go to the [Calculated Metrics page](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).
