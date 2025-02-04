---
title: Freeform table
description: Freeform tables are the foundation for data analysis in Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
---
# Freeform table {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Freeform table"
>abstract="Create an empty freeform table visualization that you can build up using dimensions, segments, metrics, and date ranges. You can use the freeform table as the basis for other visualizations."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_This article documents the Freeform table visualization in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_See [Freeform table](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table)  for the_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** version of this article._

>[!ENDSHADEBOX]


In Analysis Workspace, a ![Table](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]** visualization is the foundation for interactive data analysis. You can drag and drop a combination of [components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) into rows and columns to create a custom table for your analysis. As each component is dropped, the table updates immediately so you can quickly analyze and dig deeper.

![Freeform Table showing components in rows and columns including Visits and Online Orders for multiple web pages.](assets/opening-section.png)

To create and configure a [!UICONTROL Freeform table]:

* Add a ![Table](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]** visualization. See [Add a visualization to a panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Automated tables

The quickest way to build a table is to drop components directly into a blank project, panel or freeform table. A freeform table is built for you in a recommended format. [Watch the tutorial](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![A new Panel with the visits component dropped onto the working space.](assets/automated-table.png)

## Freeform table builder

If you prefer to add several components to your table first, then render the data, you can select **[!UICONTROL Enable table builder]**. With the builder enabled, you can drag and drop dimensions, breakdowns, metrics and filters to build tables that answer more complex questions. Data updates once you select **[!UICONTROL Build]**.

![A Freeform Table Builder showing ](assets/table-builder.png)

## Interactions

You can interact with and customize a freeform table in a variety of ways:

### Filter and sort

* You can [filter and sort](filter-and-sort.md) the data in a table.

### Rows

* You can quickly [create a new visualization](../freeform-analysis-visualizations.md#visualize) from one or more rows using ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg). 
* You can fit more rows into a single screen by adjusting the project's [view density](/help/analyze/analysis-workspace/build-workspace-project/view-density.md).
* Each dimension row can show up to 400 rows, before pagination occurs. Select the number next to **[!UICONTROL Rows]** in the first column header, to show more rows on a page. Navigate to a different page using ![ChevronRight](/help/assets/icons/ChevronRight.svg) in the first column header.
* You can break down rows by additional components. To break down many rows at once, select multiple rows and then drag the next component on top of the selected rows. Learn more about [breakdowns](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).
* Rows can be [filtered](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) to show a reduced set of items. Additional settings are available under [Row settings](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Columns

* Components can be stacked within columns to create filtered metrics, cross-tab analysis and more.
* Each column's view can be adjusted under the [column settings](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Several actions are available through the [context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). The menu provides different actions depending on if you select the table header, rows, or columns.


## Settings

Select ![Setting](/help/assets/icons/Setting.svg) to display **[!UICONTROL Table settings]**. The following specific visualization [settings](../freeform-analysis-visualizations.md#settings) are available:

### Data source

| Option | Description |
|---|---|
| **[!UICONTROL Linked visualizations]**. | Lists all linked visualizations. |
| **[!UICONTROL Show data source]** | When unchecked, the freeform table that functions as the data source for the visualization is hidden in Workspace. |

### Settings

| Option | Description |
|---|---|
| **[!UICONTROL Align dates from each columns to all start on the same row]** | To align or not align dates from each columns to all start on the same row.  |


## Context menu

The following [context menu](../freeform-analysis-visualizations.md#context-menu) options are available from the header of the visualization:

| Option | Description |
| --- | --- |
| **[!UICONTROL Insert copied visualization]**n| Paste (insert) a copied visualization to another place within the project, or into a completely different project. |
| **[!UICONTROL Copy data to clipboard]** | Copy data from the visualization onto the clipboard. |
| **[!UICONTROL Copy selection to clipboard]** | Copy the selection from the visualization onto the clipboard. |
| **[!UICONTROL Download items as CSV (*dimension name*)]** | Immediately download the dimension items (to a maximum of 50,000) of the visualization to your local device. A maximum of 50,000 dimension items for the selected dimension. |
| **[!UICONTROL Copy visualization]** | Copy the visualization, so that you can insert the visualization to another place within the project, or into a completely different project. |
| **[!UICONTROL Download data CSV]** | Immediately download the displayed data of the visualization to your local device. |
| **[!UICONTROL Duplicate visualization]** | Make an exact duplicate of the visualization. |
| **[!UICONTROL Edit description]** | Add (or edit) a text description for the visualization. See [Text](../text.md). |
| **[!UICONTROL Get visualization link]** | Copy and share a link directly to the visualization. A Share link dialog displays the link. Select Copy to copy the link to your clipboard. |
| **[!UICONTROL Start over]** | Delete the configuration for the current visualization so you can re-configure it from scratch. |



## Videos

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Freeform table builder overview](https://video.tv.adobe.com/v/31318?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Freeform table filters](https://video.tv.adobe.com/v/23232?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Freeform table totals](https://video.tv.adobe.com/v/29273?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!MORELIKETHIS]
>
>[Add a visualization to a panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualization settings](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Visualization context menu](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>



