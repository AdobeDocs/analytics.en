---
description: Shows how to build a simple "Page Views per Visits" metric.
title: Build a simple "Page Views per Visits" metric
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
---
# Build a simple "Page Views per Visits" metric

Shows how to build a simple "Page Views per Visits" metric.

For a detailed description of the UI components, see [Building Metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

Here's how to build a simple "Page Views per Visits" metric.

1. Navigate to the Calculated Metric Builder.
1. Name the metric ""Page Views per Visits" or something similar.
1. Give it a user-friendly **[!UICONTROL Description]** to show what it's used for.
1. Select the right **[!UICONTROL Format]**, in this case Decimal.
1. Decide how many decimal places you want the report to show.
1. Set the metric polarity. For this metric, an upward trend would be a good (green) thing.
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. For this metric, first drag Page Views into the canvas, then drag Visits underneath (wait until the blue line appears to drop it).
1. Select the Divide operator. (Divide is the default operator.) 
1. You can now see a **[!UICONTROL Preview]** of that metric as you are building it, at the top right.
1. Product compatibility shows you whether the metric is compatible with [Current Data](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html) or only with Fully Processed Data.
1. Click **[!UICONTROL Save]**.
1. Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.
1. You are now automatically taken to the [Calculated Metric Manager](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), which is similar to the Segment Manager. It lets you share, approve, (re-)tag, rename, or delete metrics.
