---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth. 
title: Edit entries in the Data Dictionary
feature: Components
role: Admin
---
# Edit component entries in the Data Dictionary

{{release-limited-testing}} 

Analytics administrators can edit component entries in the Data Dictionary for a given Report Suite. Any changes made are visible to all users of the Report Suite.

To edit a component in the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component that you want to edit.

1. Select the **Data Dictionary** icon in the left rail of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![Data Dictionary admin view](assets/data-dictionary-admin.png)

1. Ensure that the correct Report Suite is selected in the drop-down menu. By default, the report suite that you are already in is displayed. 

1. (Optional) In the search field, begin typing the name of the component you want to edit.

   Icons display next to component names to indicate the type of component:

   | Icon | Meaning | 
   |---------|----------|
   | ![Dimension icon](assets/dimension-icon.png) | Indicates a **dimension**. Dimensions are provided by Adobe. Existing dimensions cannot be modified and new dimensions cannot be created. |
   | ![Metric icon](assets/default-metric-icon.png) | Indicates a **standard metric** (not calculated). Standard metrics are provided by Adobe and cannot be modified. |
   | ![Adobe icon](assets/default-calc-metric-icon.png) | Indicates a **calculated metric template** or a **segment template**. These components are provided by Adobe and cannot be modified. |
   | ![Calculator icon](assets/calculated-metric-icon-created.png) | Indicates a **calculated metric** that was created by an Analytics administrator in your organization.  |
   | ![Segment icon](assets/segment-icon.png) | Indicates a **segment**. These can be segments provided by Adobe or created by an Analytics administrator in your organization.|
   | ![Date range icon](assets/date-range-icon.png) | Indicates a **date range**. These can be date ranges provided by Adobe or created by an Analytics administrator in your organization. |

{{dd-filter-criteria}}

1. From the list of components, select the component you want to edit.

1. Select the **Edit** icon ![Data Dictionary Edit icon](assets/data-dictionary-edit-icon.png) next to the component name. 

1. Edit any of the following information about the component:

   {{dd-component-information}}

1. Click the **Save** icon ![Data Dictionary Save icon](assets/data-dictionary-save-icon.png) to save your changes.
