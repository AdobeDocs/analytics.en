---
title: User Preferences
description: Learn how to set general and project preferences for users.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
---
# User Preferences

You can manage settings for Analysis Workspace and its related components for all new projects or panels that you create. Existing projects and panels are not affected.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Manage preferences](https://video.tv.adobe.com/v/332600/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Update preferences

You can update your preferences in the following ways:

- Select ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** from the Workspace main interface.
- Select **[!UICONTROL Project]** > **[!UICONTROL User preferences]** from the menu when working in a Workspace project.
- Select **[!UICONTROL Components]** > **[!UICONTROL Preferences]** from the top menu bar in Customer Journey Analytics (only available for product administrators).

## Configure preferences

You can configure the following preferences: 


## General preferences

You can customize general preferences for all new projects that you create in Analysis Workspace. For information about how to access these preferences, see [Update preferences](#update-preferences).

| Preference | Options |
| --- | --- |
| Landing page | Choose what page displays as the default page when you access Adobe Analytics: <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show tips | Displays tips in a blue box in the lower-right area of Analysis Workspace. <p>This option is enabled by default.</p> |
| Components displayed in left rail groups | Choose how many of each component to display in the Components menu in the left rail. <p>If you choose 0, the component is no longer accessible from the left rail of your workspaces.</p><p>By default, 5 components display for each of the following:</p> <ul><li>Dimensions</li><li>Metrics</li><li>Filters</li><li>Date ranges</li></ul> <p>For more information about Components in Analysis Workspace, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Company preferences {#company-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Allow sharing only with Workspace users"
>abstract="When enabled, the **[!UICONTROL Share with anyone]** option is no longer available to users when sharing an Analysis Workspace project. People who previously received access to a project through this share option can no longer access the project."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Require Experience Cloud authentication"
>abstract="When enabled, people who are given access to a project from the **[!UICONTROL Share with anyone]** option in Analysis Workspace, must authenticate using their Experience Cloud credentials."

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Allow commenting on projects"
>abstract="When enabled, a comments area is available in the right rail of each project in Analysis Workspace."


You can update company preferences that apply to all users and projects within your organization. For information about how to access these preferences, see [Update preferences](#update-preferences). 

| Section | Preference | Options |
| --- | --- | --- |
| **Templates Tab tab** | | |
|  | Hide Templates Tab | Hides the Templates Tab for all users in your organization. |
| **Project sharing** | | |
| | Allow sharing only with Workspace users | When this option is enabled, users in your organization cannot see the **[!UICONTROL Share with anyone]** option in the **[!UICONTROL Share]** menu. Users cannot share projects with people who do not have an Analysis Workspace account in your organization as described in [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).<br/>This option is disabled by default for all organizations, except for customers who have licensed Healthcare Shield. <p>Consider the following when enabling or disabling this option:<ul><li>When you enable this option, people who previously received access to a project through the **[!UICONTROL Share with anyone]** share option can no longer access the project.</li><li>If this option is enabled (to allow sharing only with Workspace users) and then later disabled (to allow sharing with anyone), people who previously received access to a project through the **[!UICONTROL Share with anyone]** share option do not automatically regain their access to the project. In this case, the user who shared the project must enable the [!UICONTROL **Link is active**] option that is available when sharing a project with anyone **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]**), as described in [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>**For customers who license Healthcare Shield:** This option is enabled by default and cannot be disabled. Before you can disable this option so that users can use the **[!UICONTROL Share with anyone]** share option, you first need to add the [!UICONTROL Share project links with anyone] permission (located under [!UICONTROL Reporting Tools]) in the Adobe Admin Console. After the permission is added, you can disable this option, then accept the resulting legal notice. For information about how to add a permission in the Admin Console, see [Manage product permissions in the Admin Console](https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Require Experience Cloud authentication | When this option is enabled, people who are given access to a project from the **[!UICONTROL Share with anyone]** option in Analysis Workspace must authenticate using their Experience Cloud credentials.<p>After this option is enabled, any time a user shares a project using the **[!UICONTROL Share with anyone]** share option, the **[!UICONTROL Require Experience Cloud authentication]** option is enabled in the share dialog and it cannot be disabled by the user who is sharing the project. For information about how users can share projects with anyone, see [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link). <p> <p>Consider the following when enabling this option: <ul><li>When you enable this option, all projects that were previously shared with the **[!UICONTROL Share with anyone]** share option, and do not have the [!UICONTROL Require Experience Cloud authentication] option enabled, are deactivated.<p>If this option is enabled (to require Experience Cloud authentication) and then later disabled (to allow anyone with the link to access the project), people who previously received access to a project through the **[!UICONTROL Share with anyone]** share option do not automatically regain their access to the project. In this case, the user who shared the project must enable the [!UICONTROL Link is active] option that is available when sharing a project with anyone **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]** > **[!UICONTROL Link is active]**), as described in [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>This option is available only if SSO is implemented in your organization. For information about how system administrators can enable SSO for your organization, see [Set up identity and Single Sign-On](https://helpx.adobe.com/enterprise/using/set-up-identity.html).</p><p>If SSO is configured for your organization, check to see if any kind of auto-account creation is implemented in the console. Typically, a system administrator would set this up, as described in [Enable automatic account creation](https://helpx.adobe.com/enterprise/using/automatic-account-creation.html).</li><li>If your organization licenses Healthcare Shield, this option is enabled by default and cannot be disabled.</li></ul>|

{style="table-layout:auto"}

## Projects & Analyses preferences {#project-analyses-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Categorical palette"
>abstract="Applied to many visualizations in Analysis Workspace and Guided analysis. Each color represents a distinct categorical value."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Diverging palette"
>abstract="Applied to the Cohort table in Analysis Workspace and User growth guided analysis. This palette holds a numeric meaning with two extremes and a baseline in the middle."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Sequential palette"
>abstract="Applied to the Frequency trends (stacked bar) guided analysis. This palette holds a numeric meaning from light to dark."

You can customize project preferences for all new projects that you create in Analysis Workspace. For information about how to access these preferences, see [Update preferences](#update-preferences). 

Some of these same preferences can also be customized for individual projects, as described in [Projects overview](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md). 

Click the linked preference titles for more information and context about each preference. 

>[!IMPORTANT]
>
>You can no longer define the number format in the **[!UICONTROL Project & Analyses]** > **[!UICONTROL Data]** section of **[!UICONTROL User preferences]**. The number format is automatically determined by the [default language that is configured](https://experienceleague.adobe.com/en/docs/core-services/interface/features/browser-language) for the logged in user.
>

| Section | Preference | Options |
| --- | --- | --- |
| **Display** | | |
|  | [View density](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Choose how much content to display on the screen by reducing the vertical padding of the left rail, freeform tables, and cohort tables. <ul><li>Compact</li><li>Comfortable</li><li>Expanded (default)</li></ul> |
| | [Color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | Choose the visualization color palettes that are used in Analysis Workspace.<ul><li>**Categorical palette**: Applied to many visualizations in Analysis Workspace. Each color represents a distinct categorical value. Choose from Adobe-provided options or enter a custom palette defined by comma-delimited hex values.</li><li>**Divergent palette**: Applied to the Cohort table in Analysis Workspace. This palette holds a numeric meaning with two extremes and a baseline in the middle.</li><li>**Sequential palette**: Applied to the Frequency trends (stacked bar) guided analysis. This palette holds a numeric meaning from light to dark.</li></ul> |
| **Data** | | |
|  | [Report suite](/help/analyze/analysis-workspace/c-panels/panels.md) | Choose from where tables and visualizations derive their data. <ul><li>Most recent (default)</li><li>Specific report suite selected from a list</li></ul> |
|  | [Calendar](/help/analyze/analysis-workspace/c-panels/panels.md) | Select from a list of: <ul><li>Adobe-provided ranges (default is This Month)</li><li>Custom-defined ranges</li></ul> |
|  | [Panel Type](/help/analyze/analysis-workspace/c-panels/panels.md) | <ul><li>Freeform (default)</li><li>Blank</li><li>Quick Insights</li></ul> |
|  | Count repeat instances | Specifies whether repeat instances are counted in reports. For example, this setting (when activated) treats multiple consecutive page views to the same page as multiple page views. With it off, they count as a single page view. <p>**Note:** This setting affects only certain metrics (such as Single Page Visits) and it does not apply to Flow or Fallout visualizations.</p> |
|  | CSV separator character | <ul><li>Comma (default)</li><li>Semicolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Space</li><li>Tab</li></ul> |
|  | Show annotations | Choose whether annotations are visible in your projects. For more information about annotations, see [Annotations overview](/help/analyze/analysis-workspace/components/annotations/overview.md). |

## Freeform table preferences {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Show anomalies"
>abstract="Selecting **[!UICONTROL Show anomalies]** automatically runs anomaly detection on the first metric column added to a time series Freeform table visualization."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Show forecast"
>abstract="Selecting **[!UICONTROL Show forecast]** automatically forecasts the first metric column added to a time series Freeform table visualization."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Default table metric"
>abstract="Select the default metric to use for freeform tables. If the selected report suite does not contain the selected default metric, the table automatically switches to another primary metric."


You can customize freeform table preferences for all new projects that you create in Analysis Workspace. For information about how to access these preferences, see [Update preferences](#update-preferences). 

Some of these same preferences can also be customized for individual tables.

Click the linked section titles for more information and context about the available preferences.

| Section | Preference | Options |
| --- | --- | --- |
| **Table** | | |
| | Table type | <ul><li>Freeform</li><li>Table builder</li></ul> |
| | Default table metric | <ul><li>Occurrences</li><li>Unique Visitors</li><li>Visits</li></ul> |
| | Default table dimension | Choose from Minute, Hour, Day, Week, Month, Quarter, or Year. |
| | Align dates | Select this option to align dates from each column to all start on the same row. |
| **[Column](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Wrap header text | Wrap the header text in Freeform tables to make headers more readable and tables more shareable. Wrapping is useful for PDF rendering and for metrics with long names. Enabled by default. |
| | Show totals | This total is typically equal to or a subset of the [!UICONTROL Grand total]. It reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option. |
| | Show grand totals | This total represents all hits that have been collected, sometimes referred to as *report suite total*. When a segment is applied either at the panel level or within the freeform table, this total adjusts to reflect all hits that match the segment criteria. Grand total is not supported for tables or breakdowns with [static rows](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Show sparkline  | Show or hide line charts at the bottom of the chart. When hidden, the legend changes to no longer visually reference the lines. |
| | Number | Determines if a cell shows/hides the numeric value for the metric. For example, if the metric is page views, the numeric value is the number of page views for the row item. |
| | Percent | Determines if a cell shows/hides the percent value for the metric. For example, if the metric is page views, the percent value is the number of page views for the row item divided by the total page views for the column.  Note: To be more accurate: percentages greater than 100% are sometines shown. The upper bound cap is moved to 1,000% to ensure that columns can grow in widths too large. |
| | Show anomalies | Determines if anomaly detection is run on the values in this column. |
| | Interpret zero as no value | For cells with a 0 value, determines whether to show a 0 or a blank cell. This is useful when you look at data for each day of a month, and some days haven't happened yet.  Instead of showing 0's for future dates, blank cells can be shown instead. Charts respect this setting as well (that is, they do not show a line or bar with 0 values when this setting is checked). |
| | Background | Determines if a cell shows/hides all cell formatting, including the bar graph and conditional formatting <ul><li>Bar graph</li> A horizontal bar graph representing the cell's value relative to the total for the column. <li>Conditional formatting</li>For more information about conditional formatting, see "Conditional formatting" in [Column Settings](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Cell preview | A preview of how each cell appears with the currently selected formatting options applied. |
| **[Row](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Breakdown by position | Select this option if you want the breakdown to remain with the position of the item rather than with the item itself. For more information about breakdowns, see [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md). |
| | Percentage calculation | <ul><li>Column</li><li>Row</li></ul> |
| | Column totals (Static rows only) |<ul><li>Display sum of rows: Shows the sum of the individual line items </li><li>Display grand total: Shows the de-duplicated sum of rows.</li></ul> |

## Visualizations preferences

You can update visualization preferences for all new projects that you create in Analysis Workspace. For information about how to access these preferences, see [Update preferences](#update-preferences). 

Some of these same preferences can also be customized for individual visualizations. 

Click the linked section titles for more information and context about the available preferences. 

| Section | Preference | Options |
| --- | --- | --- |
| **General Defaults** | | |
| | Percentages | Displays values in percentages for all visualizations. |
| | Legend visible | Lets you hide the detailed legend text for all visualizations.  |
| | Limit max items | Reduces the number of items on the X-axis for all visualizations. This can be useful if you have a large data set.  |
| | Display dual axis (when applicable) | Applies only if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This setting is helpful when plotted metrics are of very different magnitudes.  |
| | Normalization (when applicable) | Forces metrics to equal proportions. This setting is helpful when plotted metrics are of very different magnitudes.  |
| | Anchor Y-axis at zero | If all the values plotted on the chart are considerably above zero, the chart default makes the bottom of the y-axis NON-ZERO. If you check this box, the y-axis is forced to zero (and it re-draws the chart).  |
| | Allow anomalies to scale Y-axis | If you have multiple metrics in a chart, you have to hover over each anomaly to see the confidence band for that metric. To make the visualization more legible, the Anomaly Detection confidence interval does not automatically scale the y-axis. This option allows the confidence interval to scale the visualization. <p>For more information, see [View anomalies in Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p>  |
| **[Line](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | Percentages  | Displays values in percentages for the Line visualizations. |
| | Legend visible | Hide the detailed legend text for the Line visualization. |
| | Limit max items | Reduces the number of items on the X-axis in the Line visualization. This setting is useful if you have a large data set. |
| | Display dual axis (when applicable) | Applies only if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This setting is helpful when plotted metrics are of very different magnitudes. |
| | Normalization (when applicable) | Forces metrics to equal proportions. This setting is helpful when plotted metrics are of very different magnitudes. |
| | Show x-axis | Displays the x-axis on the Line chart. |
| | Show y-axis | Displays the y-axis on the Line chart.  |
| | Anchor Y-axis | If all the values plotted on the chart are considerably above zero, the chart default makes the bottom of the y-axis NON-ZERO. If you check this box, the y-axis is forced to zero (and it re-draws the chart). |
| | Show min | Overlay a minimum value label to highlight quickly the valleys in a metric. Note: The min values are derived from the visible data points in the visualization, not the full set of values within a dimension. |
| | Show max | overlay a maximum value label to highlight quickly the peaks in a metric. Note: The max values are derived from the visible data points in the visualization, not the full set of values within a dimension. |
| | Show trendline | Show a regression or moving average trendline to your line series. Trendlines help to depict a clearer pattern in the data. |
| **[Cohort](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularity | For trended visualizations, you can change the time granularity (Day, Week, Month, Quarter, or Year). This change also applies to the data source table. |
| | Only show percent | Removes the number value and only shows the percentage. |
| | Round percent to nearest whole | Rounds the percent value to the nearest whole instead of showing the decimal value. |
| | Show average percent row | Inserts a new row at the top of the table and then adds the average for the values within each column.  |
| | Cohort Preview | A preview of how the color palette appears in the cohort visualization. |
| | Cohort Palette | The color palette used in the cohort visualization. |
| **[Combo charts](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Show X-axis | Displays the x-axis on the Combo chart. |
| | Show Y-axis | Displays the y-axis on the Combo chart. |
| | Display barbells on lines | Show barbells on lines in Combo charts. |
| **[Key Metric Summary](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | Summary display type | <ul><li>Emphasize percent change</li><li>Emphasize number value</li></ul> |
| | Show sparklines | how or hide line charts at the bottom of the chart. When hidden, the legend changes to no longer visually reference the lines. |
| | Show max and min on sparklines | Show minimum and maximum values on primary and comparison line charts. |
| | Show comparison | Show comparison data. When hidden, both the comparison line chart and summary change objects are hidden from view. |
| | Number value options | In the [!UICONTROL **Key Metric Summary**] section <ul><li>Show percent change</li><li>Show raw difference</li>Raw difference between the total value of the metric in the primary date range and the secondary date range</ul> |
| **[Fallout](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Container | Switch between Visit and Visitor to analyze visitor pathing. The default is Visitor. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit. <p>The following options are available:</p> <ul><li>Visit</li><li>Visitor</li></ul> |
| **[Flow](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Container | In the [!UICONTROL **Flow**] section <ul><li>Visit</li><li>Visitor</li></ul> |
| | Wrap labels | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box. Default = unchecked. |
| | Include repeat instances | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, for example, Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. Default = unchecked. |
| | Show tooltips | Determines whether tooltips, containing node data, are shown when you hover over individual nodes within a flow visualization. |
| | Number of columns | Determines how many columns you want in your Flow diagram. |
| | Items expanded per column | How many items you want in each column. |
| **Stacked Charts** | | |
| | 100% stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. <p>For more information, see [Bar and bar stacked](/help/analyze/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | Number of buckets | Choose the number of data ranges (buckets) in the visualization. The maximum number of buckets is 50. <p>For more information, see [Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md).</p> |
| | Counting method | Choose from the following options: <ul><li>Hit</li><li>Visit</li><li>Visitor</li></ul> <p>For example, when used with page views, you could choose page views per visitor, page views per visit, or page views per hit. For Hit, "Occurrences" is used as the y-axis metric in a freeform table.</p> |
| **[Map](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | Plotting dimension | <ul><li>Mobile latitude/longitude</li><li>Geographic dimension</li></ul> |
| | Map type | <ul><li>Bubbles</li><li>Heat map</li></ul> |
| | Color theme | Choose from Coral, Reds, Greens, Blues, Heatmap, and Positive/Negative. |
| | Map style | Choose from Basic, Streets, Bright, Light, Dark, and Satellite. |
| **[Summary Change](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Value | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Percent change</li><li>Raw difference</li></ul>  |
| | Percentages | Displays values in percentages for the Summary Change visualizations. |
| | Legend visible | Lets you hide the detailed legend text for the Summary Change visualization. |
| | Abbreviate value | When selected, specify number of Decimal places. |
| **[Summary Number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Percentages | Displays values in percentages for the Summary Number visualizations. |
| | Legend visible | Lets you hide the detailed legend text for the Summary Number visualization. |
| | Summary value by | Choose from Max, Min, Mean, Median, and Sum. |
| | Abbreviate value | When selected, specify number of Decimal places. |
| **[Treemap](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | Percentages | Displays values in percentages for the Treemap visualizations. |
| | Limit max items | Reduces the number of items on the X-axis in the Treemap visualization. This can be useful if you have a large data set. |
| **[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | Legend visible | Lets you hide the detailed legend text for the Venn visualization. |
| **[Scatter](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Percentages | Displays values in percentages for the Scatter visualizations. |
| | Legend visible | Lets you hide the detailed legend text for the Scatter visualization. |
| | Limit max items | Reduces the number of items on the X-axis in the Scatter visualization. This can be useful if you have a large data set. |
| | Anchor y-axis at zero | If all the values plotted on the chart are considerably above zero, the chart default makes the bottom of the y-axis NON-ZERO. If you check this box, the y-axis is forced to zero (and it re-draws the chart). |

## Restore default preferences

You can restore all your user preferences to the system defaults. This option does not affect administrator preferences under the **[!UICONTROL Company]** tab. This action cannot be undone.

1. In Adobe Analytics, select [!UICONTROL **Components**] **>** [!UICONTROL **Preferences**] from the top menu. Or select **[!UICONTROL Project]** > **[!UICONTROL User settings]** from the Workspace menu.

1. In the upper-right, select **[!UICONTROL Restore defaults]**.

1. Select **[!UICONTROL Restore defaults]** in **[!UICONTROL Restore system default settings]**.

## [!UICONTROL Dark theme]

If you prefer to have a dark background for your Customer Journey Analytics user interface, you can toggle to [!UICONTROL Dark theme].

1. Select the Experience Cloud user icon at the top right.

   ![dark-theme](assets/dark-theme.png)

1. Enable **[!UICONTROL Dark theme]**.

