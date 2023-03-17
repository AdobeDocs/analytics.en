---
description: If you use a common variable, such as q, to populate search terms, you can use processing rules to populate the Internal Search Terms eVar with these values.
subtopic: Processing rules
title: Populate internal search terms using a query string parameter
feature: Admin Tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
---
# Populate internal search terms using a query string parameter

If you use a common variable, such as q, to populate search terms, you can use processing rules to populate the Internal Search Terms eVar with these values.

 Query string values must be encoded in Unicode or UTF-8 to be read by processing rules.

|  Rule Set  | Value  |
|---|---|
|  Condition  | If Query String Parameter q Is Set  |
|  Action  | Overwrite value of Internal Search Terms to Query String Parameter q  |

For example:

![](assets/populate-internal-search-terms.png)
