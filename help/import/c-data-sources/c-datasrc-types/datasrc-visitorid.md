---
description: Visitor IDs can be integrated by selecting the Generic (Transaction ID) category.
subtopic: Data sources
title: Visitor ID
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
---
# VisitorID

Visitor IDs can be integrated by selecting the [!UICONTROL Call Center Data] category.

See [Integrate Offline Data](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## VisitorID Dimensions

| Column Name  | Description  |
|--- |--- |
| VisitorID | (Required) Unique value that represents a customer in both the online and offline systems. |
| Date | Use the following date format: `MM/DD/YYYY/hh/mm/ss` (for example, 07/14/2017/06/00/00) |
| Tracking Code | Tracking code name.|
| Category | Category name. If you specify a category, then you must also select a product. |
| Channel | Channel name. |
| eVar*n* | eVar*n* name. Valid values for *n* are whole number 1 - 75. |
| Product | Product name. |
| State | State name. |
| Zip | Zip name. |

## Visitor ID Metrics

| Column Name  | Description  |
| --- | --- |
| Clickthroughs | Number of tracking code views. |
| Cart Adds  |Number of cart additions. |
| Cart Opens | Number of cart opens. |
| Cart Removes | Number of cart removals. |
| Cart Views | Number of cart views.|
| Checkouts | Number of checkouts. |
| Event*n* | Number of times even*n* occurred. Valid values for n are whole number 1 - 100.  If you specify a [!UICONTROL View] event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value. |
| eVar*n* Views | Number of times eVar*n* was viewed. Valid values for *n* are whole number 1 - 75.|
| Price | Product price.|
| Orders  |Number of orders placed.|
| Product Views | Number of product views.|
| Quantity | Number of units sold.|
