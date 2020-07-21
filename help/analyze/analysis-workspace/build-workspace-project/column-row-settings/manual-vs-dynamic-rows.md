---
description: How to interact with dynamic and static items in tables.
title: Dynamic vs Static items
uuid: caf033ef-d252-4f8a-802e-7edbbac5c8c0
---

# Dynamic vs Static items in freeform tables
In Freeform tables, the rows and columns can contain various component items in them. These items can be dynamic (change with time) or static (do not change with time) depending on the analysis you want to build.

## Dynamic items
Dynamic items will change with time and are dependent on the metric being sorted by in the freeform table. Dynamic items are preferred when you want to analyze the top component items for a given time period.

When you drop a dimension into a freeform table, dynamic rows are returned and represent the top items that correspond to the dimension, for a given metric and time period. You can also drop a dimension into freeform table columns and the dimension will automatically expand into the top 5 items for the dimension.

For example, when you drag the Browser Type dimension into the table, the top Browser Type dimension items (e.g. Microsoft, Apple, Google, etc.) dynamically return to the table rows. If dropped into the column, the top 5 Browser Type dimension items dynamically return.

Dynamic items will have the row filter option, and will **not** have lock and X icons present on the item.

## Static items
Static items will not change with time; they are fixed items that will always be returned to the freeform table. Static items are preferred when you want to always analyze the same item, whether it be specific campaigns or specific days in the week.

Any time you manually select and drop specific components (dimension item, metric, segment, date range) into a table, the result is a hardcoded or static list of rows or columns. Static items will also be created if you choose to:
* From rows, Right-click > Display only selected rows
* From columns, Right-click > Make item static

For example, when you drag over specific Browser Type items such as Microsoft and Apple, those 2 specific items will always get pulled into the table. 

Static items will **not** have the row filter option, and will have lock and X icons present on the item. The X means the item can be easily removed from the table.

### Mixed dimension items
Dimension items from different dimensions can be added to rows of a table; the row header will say "Mixed Dimensions". These items are static items. For example, add items from the Browser Type dimension and other items from the Browser dimension.

## Freeform total rows
Dynamic and static rows behave differently in the freeform total row. By default:
* Dynamic rows are summed server-side and de-duplicate metrics such as visits or visitors
* Static rows are summed client-side and will **not** de-duplicate metrics. 

[Learn more about Workspace total](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) options for dynamic and static rows.
