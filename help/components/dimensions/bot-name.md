---
title: Bot name
description: 
---
# Bot name

The 'Bot name' dimension shows the names of the bots detected using [Bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). These rules can be default IAB rules, or custom bot rules that your organization configures. It is helpful in cases where you want to learn more about what bots are visiting your site, or which bots generate the most traffic.

Hits that match [!UICONTROL Bot rules] are automatically filtered out of all of Analytics reporting with exception to this dimension, [Bot occurrences](../metrics/bot-occurrences.md), and [Bot page views](../metrics/bot-page-views.md). You can use this dimension and these two metrics to see what bot data is excluded from the rest of your reports.

Since bot reporting is separated from the rest of your report suite data, only the following dimensions and metrics are supported with this dimension:

* [Page](page.md)
* Time-based dimensions ([Day](day.md), [Week](week.md), [Month](month.md), etc.)
* [Bot occurrences](../metrics/bot-occurrences.md)
* [Bot page views](../metrics/bot-page-views.md)

Using any other dimension or metric with this dimension does not return data.

## Populate this dimension with data

If you have enabled [Bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), this dimension automatically collects data. If you have not yet enabled [!UICONTROL Bot rules], this dimension does not appear in Analysis Workspace.

## Dimension items

Each dimension item lists the name of the bot that matched IAB or custom bot rule criteria.
