---
description: Segmenting on individual metrics allows you to make metric comparisons within the same report. 
title: Segmented metrics
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
---
# Segmented metrics

In the [Calculated metric builder](cm-build-metrics.md#definition-builder), you can apply segments within your metric definition. Applying segments is helpful if you want to use metrics for a subset of your data in your analysis. 

>[!NOTE]
>
>Segment definitions are updated through the [Segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md). If you make a change to a segment, the segment is automatically updated everywhere it is used, including if the segment is part of a calculated metric definition.
>

You want to compare metrics for German people interacting with your brand versus people outside of Germany. So, you can answer questions like:

1. How many German versus international people are visiting your most [popular pages](#popular-pages).
1. How many German versus international people in [total](#totals) have interacted online with your brand this month.
1. What are the [percentages](#percentages) of Germans and international people that have visited your popular pages?
   
See the sections below to illustrate how segmented metrics can help you answer these questions. Where appropriate, references are made to more detailed documentation.

## Popular pages

1. [Create a calculated metric](../cm-workflow.md) from a Workspace project, named `Germany`.
1. From within the [Calculated metric builder](cm-build-metrics.md), [create a segment](/help/components/segmentation/segmentation-workflow/seg-build.md), titled `Germany`, that is using the Countries field. 

   >[!TIP]
   >
   >In the Calculated metric builder, you can create a segment directly using the Components panel.
   >   

   Your segment could look like.

   ![Segment Germany](assets/segment-germany.png)

1. Back in the Calculated metric builder, use the segment to update the calculated metric.

   ![Calculated metric Germany](assets/germany-visits.png)

Repeat the steps above for the international version of your calculated metric.

1. Create a calculated metric from your Workspace project, titled `Non Germany visits`.
1. From within the Calculated metric builder, create a segment, titled `Not Germany`, that is using the CRM Country field from your CRM data to determine where a person is coming from.
 
   Your segment should look like.

   ![Segment Germany](assets/segment-not-germany.png)

1. Back in the Calculated metric builder, use the segment to update the calculated metric.

   ![Calculated metric Germany](assets/non-germany-visits.png)


1. Create a project in Analysis Workspace, where you look at pages visited by German and Non-German visitors.

   ![Workspace Freeform table visualization showing German vs. International people](assets/workspace-german-vs-international.png)


## Totals

1. Create two new calculated metrics based on Grand Total. Open each of the segments created earlier, rename the segment, set the **[!UICONTROL Metric type]** for **[!UICONTROL People]** to **[!UICONTROL Grand Total]** and use **[!UICONTROL Save As]** to save the segment using the new name. For example:

   ![Total metric for Germany](assets/calculated-metric-germany-total.png)

1. Add a new Freeform table visualization to your Workspace project, showing the total pages for this year.

   ![Workspace Freeform table visualization showing German vs. International total people](assets/workspace-german-vs-international-totals.png)


## Percentages

1. Create two new calculated metrics that calculate a percentage from the calculated metrics you created earlier.

   ![Workspace Freeform table visualization showing German vs. International total people percentage](assets/calculated-metric-germany-total-percentage.png)


1. Update your Workspace project.

   ![Workspace Freeform table visualization showing German vs. International total people](assets/workspace-german-vs-international-totals-percentage.png)

