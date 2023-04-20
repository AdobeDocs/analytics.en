---
title: Bot occurrences
description: The number of hits that matched bot rules.
---
# Bot occurrences

The 'Bot occurrences' metric shows the number of hits that matched [Bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Since bot reporting is separated from the rest of your report suite data, this metric only works with the following dimensions:

* [Bot name](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Time-based dimensions (for example, [Day](day.md), [Week](week.md), or [Month](month.md)).

Using any other dimension with this metric does not return data.

## How this metric is calculated

Adobe checks every hit to see if it matches bot rules that your organization has configured. If a given hit matches a bot rule, the hit is excluded from reporting, and this metric increases by one. This metric includes both page views ([`t()`](/help/implement/vars/functions/t-method.md)) and link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)), whereas [Bot page views](bot-page-views.md) does not include link tracking hits.
