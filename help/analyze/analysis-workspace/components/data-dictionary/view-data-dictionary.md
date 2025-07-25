---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth.
title: View the Data Dictionary
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
---
# View component information in the Data Dictionary

The Data Dictionary allows you to view information about a component, including the component description, similar components, other components a component is frequently used with, and more.

To view information about a component in the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component that you want to view.

1. Select the [!UICONTROL **Data Dictionary**] icon in the left rail of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in [Access the data dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary).)

   The Data Dictionary window displays.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Ensure that the Report Suite that contains the component you want to view is selected in the drop-down menu. By default, the report suite that you are already in is displayed.

1. (Optional) In the search field, begin typing the name of the component you want to view.

   The type of component can be identified by both color and icon. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Segments** ![Segment icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green. The Adobe icon indicates either a calculated metric template or a segment template, and the calculator icon ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicated a calculated metric that was created by an Analytics administrator in your organization.   

1. (Optional) Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), then select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Segments**] | Show only components that are Segments. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |
   | [!UICONTROL **Missing Description**] | Show only components that do not yet have a description in the Description field. This option is available only for administrators. |
   | [!UICONTROL **Show duplicates**] | <p>Show only components that have either the same name or the same definition as that of another component in the selected Report Suite. Names or definitions must be exact matches in order to show as duplicates.</p><p>This option is available only for administrators.</p><p>**NOTE:** For definitions, this includes components you create as well as those provided by Adobe. For names, this currently includes only components you create and not those provided by Adobe. Showing duplicate names for Adobe-provided components will be added in a future release.</p> |
   | [!UICONTROL **No recent data**] | Show only components that have not collected any data in the past 90 days. This option is available only for administrators. |
   | [!UICONTROL **Created by Adobe**] <!-- I don't see this option-->| Show only components that were created by Adobe. Components that were created by an administrator or another user in your organization are not shown. |

   {style="table-layout:auto"}

1. (Optional) Select the **Sort** icon ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following filter options to sort the list of components:

   {{components-sort-options}}

1. From the list of components, select the component you want to view.

   The following information about the component is displayed:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | <p>Indicates that the component has been reviewed and approved by the administrator.</p><p>After a component is approved, administrators can remove approval by selecting the **Approved** button.</p> |
   | [!UICONTROL **Approval needed**] | <p>Indicates that the component has not yet been reviewed and approved by the administrator.</p><p>Administrators see an option to [!UICONTROL **Approve**]. Selecting this option marks the component as "Approved" to users.</p> |
   | [!UICONTROL **Description**] | Describes the intended function of the component. (This information is added by the Analytics administrator, as described in [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | [!UICONTROL **Frequently used with**] | <p>Shows components that are most commonly used with the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Segment, and Date Range.</p><p>This list is based on data from the past 90 days. Only components that you have access to view are shown.</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** filter to ensure you are seeing any components that are not shared with you.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | [!UICONTROL **Similar to**] | <p>Shows components with similar names to the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Segment, and Date Range.</p><p>Only components that you have access to view are shown.</p><p>Any duplicate components in your report suite also display here. Analytics administrators should identify and remove all duplicate components, as described in [Monitor Data Dictionary health](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** filter to ensure you are seeing any components that are not shared with you.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTE:** Currently, the **Similar to** section includes only components you create and not those provided by Adobe. Adobe-provided components will be added in a future release.</p>  |
   | [!UICONTROL **Tags**] | Shows all tags that are applied to the component. Users with administrator access can add tags when editing the component. |
   | [!UICONTROL **Component type**] | Lists the type of component it is, whether a Dimension, Metric, Segment, or Date Range. |
   | [!UICONTROL **Created by**] | Displays the name of the user who created the component. |
   | [!UICONTROL **Preview**] | Shows a preview of how the component looks in Analysis Workspace. |
   | [!UICONTROL **Date last modified**] | Displays the day the component was last modified. This section is displayed when viewing Segments, Calculated metrics, and Date ranges. |

   {style="table-layout:auto"}

1. (Optional) Drag a component from the Data Dictionary into Analysis Workspace.
