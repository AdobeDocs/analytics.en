---
title: Derive data impacted by events
description: Use calculated metrics to correct trended data impacted by an event.
---

# Derive data impacted by events

If you have data [impacted by an event](/help/technotes/event-impacted.md), you can use calculated metrics to derive trended values for the duration of the event. For example, if you had an event that caused a 25% drop in data, you can use that as a multiplier in a calculated metric. This method is helpful if you do not have the time or resources to insert data into Adobe Analytics using [Data sources](/help/import/c-data-sources/datasrc-home.md) or the [Data insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md).

>[!NOTE] These steps work best when you understand the impact of an event, both from a segmentation and date comparison perspective. Make sure to follow [Compare dates impacted by an event to previous ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) and [Exclude specific dates in analysis](../c-segmentation/use-cases/exclude-date-range.md) before following this page.

1. Create two segments for 'Affected days' and 'Exclude affected days', as outlined under [Exclude specific dates in analysis](../c-segmentation/use-cases/exclude-date-range.md).
2. Navigate to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Click **[!UICONTROL Add]**.
4. Drag both of the above segments to the definition canvas. Change the operator between them to a `+` to sum them.
5. Add the desired metric inside both segments. For example, you could use the 'Visits' metric.

   ![Segment builder](assets/event_segment_builder.png)

6. Click **[!UICONTROL Add]** in the upper right of the 'Affected days' container, then click **[!UICONTROL Static number]**. Set the static number to the percent that you want to offset your data, as outlined under [Compare dates impacted by an event to previous ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md). In this example, the offset is 25%, or 1.25.

   ![Static number](assets/event_static_number.png)

7. Apply the "corrected" metric side-by-side in a trended freeform table. All days outside the event reflect their normal metric count, while all affected days use the multiplier offset.

   ![Corrected metric](assets/event_corrected.png)

8. View the data in a line visualization to see the effect of your corrected metric.

   ![Corrected line](assets/event_line.png)
