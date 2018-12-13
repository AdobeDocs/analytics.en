---
description: Transaction IDs can be integrated by selecting the Generic (Transaction ID) category.
seo-description: Transaction IDs can be integrated by selecting the Generic (Transaction ID) category.
seo-title: Transaction ID
solution: Analytics
subtopic: Data sources
title: Transaction ID
topic: Developer and implementation
uuid: f3370bb7-3f28-460b-a20d-c9e58d7301d4
index: y
internal: n
snippet: y
---

# Transaction ID

Transaction IDs can be integrated by selecting the Generic (Transaction ID) category.

See [Integrating Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Transaction ID Dimensions** 

| Column Name  | Description  |
|--- |--- |
|Transaction ID|(Required) Unique value that represents an online transaction that resulted in offline activity.|
|Date|Use the following date format:  MM/DD/YYYY/HH/mm/SS (for example,  01/01/2015/06/00/00)|
|Tracking Code|Tracking code name.|
|Category|Category name.  If you specify a category, then you must also select a product.|
|Channel|Channel name.|
|eVarn|eVarn name. Valid values for n are whole number 1 - 250.|
|Product|Product name.|
|State|State name.|
|Zip|Zip name.|

<p class="head"> <b>Transaction ID Metrics</b> </p>



| Column Name  | Description  |
|--- |--- |
|Clickthroughs|Number of tracking code views.|
|Cart Adds|Number of cart additions.|
|Cart Opens|Number of cart opens.|
|Cart Removes|Number of cart removals.|
|Cart Views|Number of cart views.|
|Checkouts|Number of checkouts.|
|Event n|Number of times event n occurred. Valid values for n are whole number 1 - 1000.  If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value.|
|eVarn Views|Number of times eVar n was viewed. Valid values for n are whole number 1 - 250.|
|Price|Product price.|
|Orders|Number of orders placed.|
|Product Views|Number of product views.|
|Quantity|Number of units sold.|