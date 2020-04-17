---
title: Analyze data impacted by events
description: Understand how data impacted by an event contributes to overall data quality.
---

# Analyze data impacted by events

Sometimes an event can impact data quality in your organization. Examples include:

* A bot sending outlier data, such as millions of dollars in revenue
* Your organization pushed an update to your website that negatively impacted your Analytics implementation
* Other issues that affect data quality or completeness

If your site experienced data quality issues, implementation issues, or other gaps in data, you might want to exclude it from reporting to prevent making decisions on partial data. Use these sections to gauge the impact of the event on your data, and determine how you want to proceed.

## Analyze and exclude data using segmentation

Adobe Analytics offers a simple and robust way to focus on or exclude data using segmentation. You can use date range dimensions within segments to filter out or focus on those specific dates. See [Exclude specific dates in analysis](/help/components/c-segmentation/use-cases/exclude-date-range.md) in the Components user guide.

## Compare an event to previous date ranges

If you want to learn more about how much impact an event made on your data over time, you can use date comparison in Analysis Workspace. This feature lets you compare data day-by-day, week-by-week, or month-by-month to see how it compares with previous ranges. You can then use this comparison to determine how much an event affects trends. See [Compare dates impacted by an event to previous ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) in the Analyze user guide.

## Use a calendar event in Reports & Analytics

If you use Reports & Analytics, you can use a [calendar event](/help/components/t-calendar-event.md) to highlight affected days in any trended report. This method does not apply to Analysis Workspace.

1. Navigate to **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**.
2. Enter the desired title, date range, and note text.
3. Click **[!UICONTROL Save]**.

![Calendar event](assets/exclude_calendar_event.jpg)
