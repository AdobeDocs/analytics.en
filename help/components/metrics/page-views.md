---
title: Page Views
description: The number of times a dimension item was set or persisted in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
TQID: https://experienceleague.adobe.com/ZJOoxc3imuMfVTa7caV5eQ6-XJh0amCRq65ByuANFq0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Page Views

The **[!UICONTROL Page views]** [metric](overview.md) shows the number of times that a given dimension item was set or persisted on a page. It is one of the most common and basic metrics in reports.

## How this metric is calculated

This metric counts all page view tracking calls ([`t()`](/help/implement/vars/functions/t-method.md)) in a report suite. For dimensions, it includes hits where a dimension item is set or persisted. It does not include link tracking calls ([`tl()`](/help/implement/vars/functions/tl-method.md)) or data from [Data sources](/help/import/data-sources/overview.md).

## Compare to similar metrics

* **Page views vs. [Visits](visits.md)**: Page views count the number of times that a page is viewed. Visits count the number of sessions for visitors. One visit consists of one or more page views.
* **Page views vs. [Page events](page-events.md)**: Page views count the number of page view tracking calls (`t()`), and exclude link tracking calls (`tl()`). Page events are the opposite; they count the number of link tracking calls, and exclude page view tracking calls.
