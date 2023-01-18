---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth. 
title: View the Data Dictionary
feature: Data Dictionary
role: User, Admin
---
# View component information in the Data Dictionary

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment. 

For general information about the Data Dictionary, see [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

To view information about a component in the Data Dictionary (including the component description, similar components, other components a component is frequently used with, and more):

1. Go to the Analysis Workspace project that contains the component that you want to view.

1. Select the Data Dictionary icon on the left side of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![data-dictionary.png](assets/data-dictionary.png)

1. Ensure that the Report Suite that contains the component you want to view is selected in the drop-down menu. 

1. In the search field, begin typing the name of the component you want to view.

{{dd-filter-criteria}}

1. From the list of components, select the component you want to view.

   The following information about the component is displayed:

   {{dd-component-information}}

   * [!UICONTROL **Description**]: Describes the intended function of the component. 

     This information is added by the Analytics administrator, as described in [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

   * [!UICONTROL **Frequently used with**]: Shows the 5 components that are most commonly used with the component you are viewing. This list is based on data from the past 90 days. Only components that you have access to view are shown. 

   * [!UICONTROL **Similar to**]: Shows 5 components with similar labels to the component you are viewing. Only components that you have access to view are shown.

   * [!UICONTROL **Popular with**]: Shows which users frequently use the component you are viewing.

   * [!UICONTROL **Tags**]: 

   * [!UICONTROL **Component type**]: Lists the type of component it is, whether a Dimension, Metric, Segment, or Date Range. 

   * [!UICONTROL **Created by**]: Displays the name of the user who created the component.

   * [!UICONTROL **Preview**]: Shows a preview of how the component looks in Analysis Workspace.

   * [!UICONTROL **Date last modified**]: Displays the day the component was last modified. This section is displayed when viewing Segments, Calculated metrics, and Date ranges. <!--for CJA, it is displayed for all components--> 



