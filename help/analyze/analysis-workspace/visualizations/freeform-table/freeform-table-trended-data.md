---
description: Learn how to view trended data for a freeform table in Analysis Workspace.
title: View trended data for a freeform table
feature: Freeform Tables
role: User, Admin
---
# View trended data for a freeform table

You can view the trend of the data that is included in a freeform table. This trended data shows in the following areas within Analysis Workspace:

* [Sparklines](#use-sparklines-to-view-trended-data)

* [Line visualizations](#use-line-visualizations-to-view-trended-data)

## Use sparklines to view trended data

Sparklines are shown in the metric column header of freeform tables.

  ![sparkline in freeform table](assets/table-sparkline.png)

Sparklines always include:

* Trended data for all data in the column

* Any filter criteria that is applied on the table filter

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Use line visualizations to view trended data

[Line](/help/analyze/analysis-workspace/visualizations/line.md) visualizations display the data of the freeform table they are connected to.

### Connect a line visualization to a freeform table

1. Add a line visualization to an Analysis Workspace project.

1. Select the dot next to the visualization name, select the **[!UICONTROL Data source]** tab, then select the name of the freeform table that you want to connect to the line visualization. 

   ![line visualization connected to freeform tables](assets/table-line-viz.png)

### Choose the data that is included in the line visualization

The data that is included in the connected line visualization differs, depending on whether the sparkline is selected.

When the sparkline is selected, the cell displays as dark gray.

![sparkline selected](assets/table-sparkline-selected.png)

When the sparkline of the connected table is selected, line visualizations include:

* Trended data for all data in the column

* Any filter criteria that is applied on the table filter

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

When the sparkline of the connected table is not selected, line visualizations include:

* Data for the first dimension only of the connected table

* Any filter criteria is ignored

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


## Include filter criteria in connected line visualizations 

Any filter criteria that you apply to a freeform table can be included in sparklines and connected line visualizations.

By default, filter criteria is not included in line visualizations and sparklines. They display data only for the first row of the freeform table. 

You can configure line visualizations and sparklines to include filter criteria. When you do, any filter criteria is applied as a segment on the metric column:

1. Select the sparkline in the metric column header. 

   When the sparkline and column total cell is selected, it displays as dark gray. This indicates that filter criteria is included in both the sparkline graph and the connected line chart graph.

   ![sparkline selected](assets/table-sparkline-selected.png)

Show what the segment looks like when it's applied.

