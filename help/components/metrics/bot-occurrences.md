---
title: Bot occurrences
description: The number of hits that matched bot rules.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
TQID: https://experienceleague.adobe.com/LH7eQC-Z6Y3nku1QzI9Yn0N3MRwGA--5R-93lfadT1c
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
# Bot occurrences

The 'Bot occurrences' [metric](overview.md) shows the number of hits that matched [Bot rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Since bot reporting is separated from the rest of your report suite data, this metric only works with the following dimensions:

* [Bot name](../dimensions/bot-name.md)
* [Page](../dimensions/page.md)
* Time-based dimensions (for example, [Day](../dimensions/day.md), [Week](../dimensions/week.md), or [Month](../dimensions/month.md))

Using any other dimension with this metric does not return data.

## How this metric is calculated

Adobe checks every hit to see if it matches bot rules that your organization has configured. If a given hit matches a bot rule, the hit is excluded from reporting, and this metric increases by one. This metric includes both page views ([`t()`](/help/implement/vars/functions/t-method.md)) and link tracking hits ([`tl()`](/help/implement/vars/functions/tl-method.md)), whereas [Bot page views](bot-page-views.md) do not include link tracking hits.
