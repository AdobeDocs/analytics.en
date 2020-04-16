---
title: Compare dates impacted by an event to previous ranges
description: Learn about the impact of an event, such as an implementation issue or outage, by comparing it to previous trends.
---

# Compare dates impacted by an event to previous ranges

If you have data [impacted by an event](/help/technotes/event-impacted.md), you can look at historical trends to gauge its impact. This comparison is valuable to understand just how much an event impacts your data, so you can decide whether to exclude the data, add a note to reports, or ignore it.

## Create a date range that includes the event

Create a date range that encompasses the event to begin exploring the impact of that event.

1. Navigate to **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.
2. Click **[!UICONTROL Add]**.
3. Select the date range where the event occurred. Click **[!UICONTROL Save]**.

   ![Date range builder](assets/date_range_builder.png)

## View event dates and similar prior ranges side-by-side

You can compare any metric between the date range of the event with similar prior date ranges using a freeform table visualization.

1. Open a Workspace project, and add the generic orange 'Day' dimension to the freeform table. Apply the recently created purple date range stacked on a green metric, such as 'Occurrences'.

   ![Date range metric](assets/date_range_metric.png)

2. Right click the purple date range, then click **[!UICONTROL Add time period column]** > **[!UICONTROL Custom date range to this date range]**.
   * For a week-over-week comparison, select the range of the event minus 7 days. Make sure that the days of the week between the event and this date range are aligned.
   * For a month-over-month comparison, select the range of the event last month. You can also select the range of the event minus 28 days if you want to align days of the week.
   * For a year-over-year comparision, select the range of the event last year.
3. When you select the desired date range, they are added to your freeform table. You can right click and add as many date ranges as you'd like to compare.

   ![Date aligned trends](assets/date_aligned_trends.png)

## Calculate percent differences between the event and similar prior ranges

Compare dimension values between an event's date range and similar prior date ranges using a freeform table visualization. These steps illustrate a week-over-week example that you can follow.

1. Open a Workspace project, and add a **non-time dimension** to the freeform table. For example, you could use the 'Mobile device type' dimension. Apply the recently created purple date range stacked on a green metric, such as 'Occurrences':

   ![Mobile device type by affected date range](assets/mobile_device_type.png)

2. Right click the purple date range, then click **[!UICONTROL Compare time periods]** > **[!UICONTROL Custom date range to this date range]**. Select the range of the event minus 7 days. Make sure that the days of the week between the event and this date range are aligned.

   ![Compare time period menu](assets/compare_time_custom.png)