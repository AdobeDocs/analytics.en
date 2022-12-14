---
title: How to set user preferences in Analysis Workspace
description: You can set general and project preferences for users, as well as a dark theme preference.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
---
# User preferences

You can manage settings for Analysis Workspace and its related components at the user-level. Changes that you make to your user preferences apply to all *new* projects or panels.

View this short video for a brief overview of user preferences:

>[!VIDEO](https://video.tv.adobe.com/v/332600/?quality=12)

## Access user preferences

1. In Adobe Analytics, [!UICONTROL **Components**] **>** [!UICONTROL **User preferences**].

   ![User preferences](assets/user-preferences.png) 

1. To adjust your user preferences, continue with the following sections in this article.

## General preferences

These settings apply to general preferences in Adobe Analytics.

| Preference | Options |
| --- | --- |
| Landing page | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Tips | <ul><li>Enabled (default)</li><li>Disabled</li></ul> |
| <span class="preview">Components displayed in left rail groups</span> | Choose how many of each component to display in the Components menu in the left rail. <p>If you choose 0, the component is no longer accessible from the left rail of your workspaces.</p><p>By default, 5 components display for each of the following:</p> <ul><li>Dimensions</li><li>Metrics</li><li>Filters</li><li>Date ranges</li></ul> <p>For more information about Components in Analysis Workspace, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Project preferences

Project preferences apply to new projects and new panels created in Analysis Workspace. Certain preferences can also be managed on a per-project basis under [!UICONTROL Workspace] > [!UICONTROL Project] > [!UICONTROL Project info & settings].

| Section | Preference | Options |
| --- | --- | --- |
| **Display** | | |
|  | [View density](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) | <ul><li>Compact</li><li>Comfortable</li><li>Expanded (default)</li></ul> |
| | [Color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html) | <ul><li>Adobe-provided palettes (default)</li><li><span class="preview">Conditional formatting palette </span></li><li><span class="preview">Up/down palette (diverging)</span><li>Custom-defined palettes</li></ul> |
| **Data** | | |
|  | [Report suites](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#report-suite) | <ul><li>Most recent (default)</li><li>Specific report suite selected from a list</li></ul> |
|  | [Calendar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?#calendar) | Select from a list of: <ul><li>Adobe-provided ranges (default is This Month)</li><li>Custom-defined ranges</li></ul> |
|  | <span class="preview">12/24 HR </span>| TBD - This is a new setting |
|  | [Panel Type](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) | <ul><li>Freeform (default)</li><li>Blank</li><li>Quick Insights</li></ul> |
|  | Count repeat instances | Specifies whether repeat instances are counted in reports. For example, this setting (when activated) treats multiple consecutive page views to the same page as multiple page views. With it off, they count as a single page view. **Note:** This setting affects only certain metrics (such as Single Page Visits) and it does not apply to Flow or Fallout visualizations. |
|  | Conditional formatting palette | TBD - This is a new setting |
|  | Number format | <ul><li>1,000.00 (default)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV separator character | <ul><li>Comma (default)</li><li>Semicolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Space</li><li>Tab</li></ul> |
|  | Freeform table | <ul><li>Show anomalies </li><li>Show sparklines</li><li>Show annotations</li></ul> |

## Freeform table preferences

<div class="preview">
Freeform table preferences apply to your Adobe Analytics experience in the browser.

| Preference | Options |
| --- | --- |
| Table type | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Default table metric | <ul><li>Enabled (default)</li><li>Disabled</li></ul> |
| Default table dimension | Choose how many of each component to display in the Components menu in the left rail. <p>If you choose 0, the component is no longer accessible from the left rail of your workspaces.</p><p>By default, 5 components display for each of the following:</p> <ul><li>Dimensions</li><li>Metrics</li><li>Filters</li><li>Date ranges</li></ul> <p>For more information about Components in Analysis Workspace, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |
| Align dates | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Wrap header text | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show totals | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show grand totals | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show sparkline <!-- this is already in the tool/docs under "Freeform table -->  | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Number | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Percent | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show anomalies <!-- this is already in the tool/docs under "Freeform table --> | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Interpret zero as no value | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Background | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Cell preview | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Breakdowns | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Percentage calculation | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
</div>

## Visualizations preferences

<div class="preview">
Visualization preferences apply to your Adobe Analytics experience in the browser.

| Preference | Options |
| --- | --- |
| Percentages | In the [!UICONTROL **General Defaults**] section |
| Legend visible | In the [!UICONTROL **General Defaults**] section  |
| Limit max items | In the [!UICONTROL **General Defaults**] section  |
| Display dual axis (when applicable) | In the [!UICONTROL **General Defaults**] section  |
| Normalization (when applicable) | In the [!UICONTROL **General Defaults**] section  |
| Anchor Y-axis at zero | In the [!UICONTROL **General Defaults**] section  |
| Allow anomalies to scale Y-axis | In the [!UICONTROL **General Defaults**] section  |
| Percentages  | In the [!UICONTROL **Line**] section |
| Legend visible | In the [!UICONTROL **Line**] section |
| Limit max items | In the [!UICONTROL **Line**] section |
| Display dual axis (when applicable) | In the [!UICONTROL **Line**] section |
| Normalization (when applicable) | In the [!UICONTROL **Line**] section |
| Show x-axis | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show y-axis | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Anchor Y-axis at zero | In the [!UICONTROL **Line**] section |
| Show min | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show max | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show trendline | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Granularity | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Only show percent | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Round percent to nearest whole | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show average percent row | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Cohort Preview | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Color Palette | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show X-axis | In the [!UICONTROL **Combo Charts**] section |
| Show Y-axis | In the [!UICONTROL **Combo Charts**] section |
| Display barbells on lines | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Summary display type | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show sparklines | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show max and min on sparklines | <ul><li>Project list (default)</li><li>Blank project</li><li>Specific project selected from a list</li></ul> |
| Show comparison | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Number value options | In the [!UICONTROL **Key Metric Summary**] section |
| Abbreviate value | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Container | In the [!UICONTROL **Fallout**] section |
| Container | In the [!UICONTROL **Container**] section |
| Wrap labels | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Include repeat instances | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Show tooltips | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Number of columns | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Items expanded per column | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| 100% stacked | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Number of buckets | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Counting method | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Plotting dimension | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Map type | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Color theme | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Map style | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Value | <!-- Seem to be basically the same options as in "Number value options" -->  |
| Percentages | In the [!UICONTROL **Summary Change**] section |
| Legend visible | In the [!UICONTROL **Summary Change**] section |
| Percentages | In the [!UICONTROL **Summary Number**] section |
| Legend visible | In the [!UICONTROL **Summary Number**] section |
| Summary value by | <ul><li>Project list (default)</li><li>Blank project</li><li>Show comparison</li></ul> |
| Percentages | In the [!UICONTROL **Treemap**] section |
| Limit max items | In the [!UICONTROL **Treemap**] section |
| Legend visible | In the [!UICONTROL **Venn**] section |
| Percentages | In the [!UICONTROL **Scatter**] section |
| Legend visible | In the [!UICONTROL **Scatter**] section |
| Limit max items | In the [!UICONTROL **Scatter**] section |
| Anchor y-axis at zero | In the [!UICONTROL **Scatter**] section |
</div>

## [!UICONTROL Dark theme]

If you prefer to have a dark background for your Adobe Analytics user interface, you can toggle to [!UICONTROL Dark theme].

1. Click the Experience Cloud user icon at the top right.

   ![dark-theme](assets/dark-theme.png)

1. Move the **[!UICONTROL Dark theme]** toggle to the right.
