---
description: Visitor IDs can be integrated by selecting the Generic (Transaction ID) category.
solution: Analytics
subtopic: Data sources
title: Visitor ID
topic: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
---

# Visitor ID

Visitor IDs can be integrated by selecting the Generic (Transaction ID) category.

See [Integrate Offline Data](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

<p class="head"> <b>Visitor ID Dimensions</b> </p>

| Column Name  | Description  |
|--- |--- |
|Visitor ID|(Required) Unique value that represents a customer in both the online and offline systems.|
|Date|Use the following date format:  MM/DD/YYYY/hh/mm/ss (for example,  07/14/2017/06/00/00)|
|Tracking Code|Tracking code name.|
|Category|Category name.  If you specify a category, then you must also select a product.|
|Channel|Channel name.|
|eVarn|eVarn name. Valid values for n are whole number 1 - 75.|
|Product|Product name.|
|State|State name.|
|Zip|Zip name.|

**Visitor ID Metrics** 

| Column Name  | Description  |
|--- |--- |
|Clickthroughs|Number of tracking code views.|
|Cart Adds|Number of cart additions.|
|Cart Opens|Number of cart opens.|
|Cart Removes|Number of cart removals.|
|Cart Views|Number of cart views.|
|Checkouts|Number of checkouts.|
|Event n|Number of times event n occurred. Valid values for n are whole number 1 - 100.  If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value.|
|eVarn Views|Number of times eVar n was viewed. Valid values for n are whole number 1 - 75.|
|Price|Product price.|
|Orders|Number of orders placed.|
|Product Views|Number of product views.|
|Quantity|Number of units sold.|
