---
title: Bot page views
description: The number of page views that matched bot rules.
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
hide: yes
hidefromtoc: yes
---
# Bot page views

The 'Bot page views' metric shows the number of page hits that matched [Bot rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Since bot reporting is separated from the rest of your report suite data, this metric only works with the following dimensions:

* [Bot name](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Time-based dimensions (for example, [Day](../dimensions/day.md), [Week](../dimensions/week.md), or [Month](../dimensions/month.md))

Using any other dimension with this metric does not return data.

## How this metric is calculated

Adobe checks every page hit to see if it matches bot rules that your organization has configured. If a given hit matches a bot rule, the page hit is excluded from reporting, and this metric increases by one. This metric does not include link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)).
