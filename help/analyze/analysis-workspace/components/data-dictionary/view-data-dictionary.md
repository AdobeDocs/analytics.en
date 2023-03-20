---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth. 
title: View the Data Dictionary
feature: Components
role: User, Admin
---
# View component information in the Data Dictionary

{{release-limited-testing}} 

The Data Dictionary allows you to view information about a component, including the component description, similar components, other components a component is frequently used with, and more.

To view information about a component in the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component that you want to view.

1. Select the [!UICONTROL **Data Dictionary**] icon in the left rail of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Ensure that the Report Suite that contains the component you want to view is selected in the drop-down menu. By default, the report suite that you are already in is displayed.

1. (Optional) In the search field, begin typing the name of the component you want to view.

   Icons display next to component names to indicate the type of component:

   | Icon | Meaning | 
   |---------|----------|
   | ![Dimension icon](assets/dimension-icon.png) | Indicates a **dimension**. Dimensions are provided by Adobe. Existing dimensions cannot be modified and new dimensions cannot be created. |
   | ![Metric icon](assets/default-metric-icon.png) | Indicates a **standard metric** (not calculated). Standard metrics are provided by Adobe and cannot be modified. |
   | ![Adobe icon](assets/default-calc-metric-icon.png) | Indicates a **calculated metric template**. These are calculated metrics that are provided by Adobe and cannot be modified. |
   | ![Calculator icon](assets/calculated-metric-icon-created.png) | Indicates a **calculated metric** that was created by an Analytics administrator in your organization. <!-- Delete all the comments... Components with this icon can be modified by an Analytics administrator. New calculated metrics can be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![Segment icon](assets/segment-icon.png) | Indicates a **segment**. These can be segments provided by Adobe or created by an Analytics administrator in your organization.<!-- Segments that were created byComponents with this icon can be modified by an Analytics administrator, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md). New calculated metrics can also be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). -->|
   | ![Date range icon](assets/date-range-icon.png) | Indicates a **date range**. These can be date ranges provided by Adobe or created by an Analytics administrator in your organization. <!-- Components with this icon can be modified by an Analytics administrator. New date ranges can also be created by an Analytics administrator, as described in [Create custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). -->|

{{dd-filter-criteria}}

1. From the list of components, select the component you want to view.

   The following information about the component is displayed:

   {{dd-component-information}}

1. (Optional) Drag a component from the Data Dictionary into Analysis Workspace. 