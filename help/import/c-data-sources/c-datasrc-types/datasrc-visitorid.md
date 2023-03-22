---
description: Visitor IDs can be integrated by selecting the Generic (Transaction ID) category.
subtopic: Data sources
title: Visitor ID
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
---
# VisitorID

Visitor IDs can be integrated by selecting the [!UICONTROL Call Center Data] category.

See [Integrate Offline Data](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## VisitorID Dimensions

| Column Name  | Description  |
|--- |--- |
| [!UICONTROL VisitorID] | (Required) Unique value that represents a customer in both the online and offline systems. |
| [!UICONTROL Date] | Use the following date format: `MM/DD/YYYY/hh/mm/ss` (for example, 07/14/2017/06/00/00) |
| [!UICONTROL Tracking Code] | Tracking code name.|
| [!UICONTROL Category] | Category name. If you specify a category, then you must also select a product. |
| [!UICONTROL Channel] | Channel name. |
| [!UICONTROL eVar]*n* | eVar*n* name. Valid values for *n* are whole number 1 - 75. |
| [!UICONTROL Product] | Product name. |
| [!UICONTROL State] | State name. |
| [!UICONTROL Zip] | Zip name. |

## Visitor ID Metrics

| Column Name  | Description  |
| --- | --- |
| [!UICONTROL Clickthroughs] | Number of tracking code views. |
| [!UICONTROL Cart Adds]  | Number of cart additions. |
| [!UICONTROL Cart Opens] | Number of cart opens. |
| [!UICONTROL Cart Removes] | Number of cart removals. |
| [!UICONTROL Cart Views] | Number of cart views.|
| [!UICONTROL Checkouts] | Number of checkouts. |
| [!UICONTROL Event]*n* | Number of times even*n* occurred. Valid values for n are whole number 1 - 100.  If you specify a [!UICONTROL View] event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value. |
| [!UICONTROL eVar]*n* Views | Number of times eVar*n* was viewed. Valid values for *n* are whole number 1 - 75.|
| [!UICONTROL Price] | Product price.|
| [!UICONTROL Orders]  |Number of orders placed.|
| [!UICONTROL Product Views] | Number of product views.|
| [!UICONTROL Quantity] | Number of units sold.|
