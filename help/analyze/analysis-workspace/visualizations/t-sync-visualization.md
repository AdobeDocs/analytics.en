---
description: Learn how to link visualizations to a freeform table data source.
keywords: Analysis Workspace;Synchronize visualization with data source
title: Manage Visualization Data Sources in Analysis Workspace
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
TQID: https://experienceleague.adobe.com/ZteQfWHbl29KbcI-OUvvjEXgKytSIuR8l5R40zWQ-Rk
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
# Manage data sources {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Lock selection"
>abstract="Enable this setting to lock the visualization to the selected positions or the selected items in the data source."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Show table"
>abstract="Selecting **[!UICONTROL Show table]** generates a new data source for your current visualization, separate from the original data source."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Show table"
>abstract="Select **[!UICONTROL Show table]** to generate a new data source for your current visualization, separate from the original data source."

Each visualization in Analysis Workspace is based on a data source, typically a freeform table. Synchronizing visualizations lets you control which freeform table or data source corresponds to a visualization, and whether the visualization stays locked to specific rows in that table.

>[!TIP]
>
>You can tell which visualizations are related by the color of ![StatusOrange](/help/assets/icons/StatusOrange.svg) next to the title of visualizations. Matching colors mean that visualizations are based on the same data source.
>

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## Configure data source settings {#configure}

1. In Analysis Workspace, go to the visualization whose data source or lock settings you want to configure.

1. Hover over the visualization, then select the **[!UICONTROL Settings]** icon ![Setting](/help/assets/icons/Setting.svg).

1. Select the **[!UICONTROL Data source]** tab.

   ![Data source tab showing the data source, linked visualization, and lock selection settings.](assets/lock-selection.png)

1. Configure any of the following settings:

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Data source]** | Select the data source on which the visualization is based. |
   | **[!UICONTROL Linked visualizations]** | Lists all visualizations linked to the data source (freeform table). |
   | **[!UICONTROL Show data source]** | Show or hide the data source (freeform table) that corresponds to the visualization. |
   | **[!UICONTROL Lock selection]** | Lock the visualization to the rows currently selected in the data source, then select **[!UICONTROL Selected positions]** or **[!UICONTROL Selected items]**. See [Lock selection](#lock-selection). |

## Lock selection {#lock-selection}

Locking the selection keeps a visualization focused on the rows you select in its data source, even when the table changes. For example, the table changes when you sort or filter it, change its date range, or apply a segment. A locked visualization shows ![LockClosed](/help/assets/icons/LockClosed.svg) next to its title.

If the segments, dimensions, or metrics in the data source change and the locked data is no longer visible, select **[!UICONTROL Show table]** to generate a new data source for the visualization, separate from the original data source.

When you lock the selection, choose one of the following options:

| Option | Description |
| --- | --- |
| **[!UICONTROL Selected positions]** | Locks the visualization to the **positions** of the rows selected in the data source. Those positions continue to be visualized, even if the items in them change. For example, select this option to always show the top five campaign names in the data source, regardless of which campaigns they are.<br><br>If you lock breakdown rows and those rows are no longer in the table, the visualization doesn't display. To display it again, update the table (for example, its date range, segments, or filters) or update the lock selection. |
| **[!UICONTROL Selected items]** | Locks the visualization to the specific **items** selected in the data source. Those items continue to be visualized, even if their ranking in the table changes. For example, select this option to always show the same five campaign names, regardless of how they rank. |
