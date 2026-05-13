---
title: Bot page views
description: The number of page views that matched bot rules.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
TQID: https://experienceleague.adobe.com/Y0r2fzF87dep4NsrbJGCC9OnqBHrZozCh2DovNc90KQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Bot page views

The 'Bot page views' [metric](overview.md) shows the number of page hits that matched [Bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Since bot reporting is separated from the rest of your report suite data, this metric only works with the following dimensions:

* [Bot name](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Time-based dimensions (for example, [Day](../dimensions/day.md), [Week](../dimensions/week.md), or [Month](../dimensions/month.md))

Using any other dimension with this metric does not return data.

## How this metric is calculated

Adobe checks every page hit to see if it matches bot rules that your organization has configured. If a given hit matches a bot rule, the page hit is excluded from reporting, and this metric increases by one. This metric does not include link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)).
