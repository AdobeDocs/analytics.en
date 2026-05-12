---
description: Learn how to view trended data for a freeform table in Analysis Workspace.
title: View trended data for a freeform table
feature: Freeform Tables
role: User, Admin
exl-id: b1d109fd-0e3c-45df-94d0-1a6383d7f995
TQID: https://experienceleague.adobe.com/-L-J1kq-YozWG8VnwD8-7637M6QlUYu3-wVeBvVBipA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
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

* Any search filter criteria applied to the table dimension

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Use line visualizations to view trended data

[Line](/help/analyze/analysis-workspace/visualizations/line.md) visualizations display the data of the freeform table they are connected to.

### Connect a line visualization to a freeform table

Depending on how and when the line visualization was added to the project, it might already be connected to the desired freeform table. Use the following steps to check or to manually connect it:

1. Add a line visualization to an Analysis Workspace project.

1. Select the dot next to the visualization name, select the **[!UICONTROL Data source]** tab, then select the name of the freeform table that you want to connect to the line visualization. 

   ![line visualization connected to freeform tables](assets/table-line-viz.png)

### Choose the data that is included in the line visualization

The data that is included in the connected line visualization differs, depending on which cell is selected in the freeform table. 

To view a trend of all data in the freeform table, select the sparkline cell in the freeform table.

When the sparkline cell is selected, the cell displays as dark gray.

![sparkline selected](assets/table-sparkline-selected.png)

When the sparkline cell of the connected table is selected, line visualizations include:

* Trended data for all data in the column

* Any search filter criteria applied to the table dimension

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

When the sparkline of the connected table is not selected, line visualizations include:

* Data for the row that is selected in the connected table. If no row is selected, data for the first dimension only of the connected table is shown.

* Any search filter criteria applied to the table dimension is ignored

  For more information, see [Filter and sort](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


## Include filter criteria in connected line visualizations 

For information about when filter criteria is included in connected line visualizations, see [Include filter criteria in trended data in sparklines and line visualizations](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)
