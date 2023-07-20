# Snippets

## Reports & Analytics end-of-life announcement {#ra-eol}

>[!IMPORTANT]
>
>Read more about the Reports & Analytics [End-of-life announcement](https://www.adobe.com/go/analytics_rnaeol_en).

## Data Dictionary filter criteria {#dd-filter-criteria}

1. (Optional) Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), then select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Segments**] | Show only components that are Segments. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |
   | [!UICONTROL **Missing Description**] | Show only components that do not yet have a description in the Description field. This option is available only for administrators. |
   | [!UICONTROL **Show duplicates**] | <p>Show only components that have either the same name or the same definition as that of another component in the selected Report Suite. Names or definitions must be exact matches in order to show as duplicates.</p><p>This option is available only for administrators.</p><p>**NOTE:** For definitions, this includes components you create as well as those provided by Adobe. For names, this currently includes only components you create and not those provided by Adobe. Showing duplicate names for Adobe-provided components will be added in a future release.</p> |
   | [!UICONTROL **No recent data**] | Show only components that have not collected any data in the past 90 days. This option is available only for administrators. |
   | [!UICONTROL **Created by Adobe**] <!-- I don't see this option-->| Show only components that were created by Adobe. Components that were created by an administrator or another user in your organization are not shown. |

   {style="table-layout:auto"}

## Data Dictionary component information {#dd-component-information}

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

## Components sort options {#components-sort-options}

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Recommended**] | Sorts components with those that are recommended at the top of the list. Components that are used most frequently and most recently by you or by others in your organization are shown higher in the list. |
   | [!UICONTROL **Alphabetical**] | Sorts components alphabetically. |
   | [!UICONTROL **Categorical**] | Sorts components according to component type (dimension, metric, segment, date range). |

   {style="table-layout:auto"}

## Release phase Limited Testing {#release-limited-testing}

>[!AVAILABILITY]
>
>The functionality described in this article is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Analytics release process, see [Adobe Analytics feature releases](/help/release-notes/releases.md).

## Release phase Limited Testing section {#release-limited-testing-section}

>[!AVAILABILITY]
>
>The functionality described in this section is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Analytics release process, see [Adobe Analytics feature releases](/help/release-notes/releases.md).


## Plug-in disclaimer {#plug-in}

>[!IMPORTANT]
>
>This plug-in is provided by Adobe Consulting as a courtesy to help you get more value out of Adobe Analytics. Adobe Customer Care does not provide support with this plug-in, including installation or troubleshooting. If you require help with this plug-in, contact your organization's Adobe Account Team. They can arrange a meeting with a consultant for assistance.

