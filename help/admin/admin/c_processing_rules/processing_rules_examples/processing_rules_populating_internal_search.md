---
description: If you use a common variable, such as q, to populate search terms, you can use processing rules to populate the Internal Search Terms eVar with these values.
seo-description: If you use a common variable, such as q, to populate search terms, you can use processing rules to populate the Internal Search Terms eVar with these values.
seo-title: Populate internal search terms using a query string parameter
solution: Analytics
subtopic: Processing rules
title: Populate internal search terms using a query string parameter
topic: Admin tools
uuid: 29c7ea74-239f-47ba-bc3d-7d9dc58db7b9
index: y
internal: n
snippet: y
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

