---
title: Report Customization in Adobe Analytics
description: Learn how to customize reports in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
---
# Customize reports

In third-party platforms such as Google Analytics, several customization options are available. These customizations allow a user to create dashboards, custom reports, saved reports, and custom alerts. Because Analysis Workspace allows users to build reports from a blank canvas, most customizations are built directly into the tool.

This page assumes the user has a basic knowledge of using [!UICONTROL Analysis Workspace]. See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Dashboards

The [!UICONTROL Analysis Workspace] architecture is built similar to the concept of dashboard widgets. Projects in [!UICONTROL Analysis Workspace] are the approximate equivalent to dashboards in Google Analytics. Visualizations in [!UICONTROL Analysis Workspace] are the approximate equivalent of widgets in Google Analytics.

### Adding content to a project

1. Click the [!UICONTROL Visualizations] icon on the left and drag the desired visualization onto the workspace.
2. Click the [!UICONTROL Components] icon on the left and drag the desired dimensions and metrics onto the visualization to populate it with data.
3. Drag the edges of the visualization to resize it, and drag the title of the visualization to move it.

All Google Analytics widgets are available in [!UICONTROL Analysis Workspace]:

* The **Metric widget** is approximately equal to the [!UICONTROL Summary Number] visualization.
* The **Timeline widget** is approximately equal to the [!UICONTROL Line] visualization.
* The **Geomap widget** is approximately equal to the [!UICONTROL Map] visualization.
* The **Table widget** is approximately equal to the [!UICONTROL Freeform Table] visualization.
* The **Pie widget** is approximately equal to the [!UICONTROL Donut] visualization.
* The **Bar widget** is approximately equal to the [!UICONTROL Bar] visualization.

[!UICONTROL Analysis Workspace] includes many more visualization options to present data in a way best fit for your reporting needs. See [Visualizations in Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### Sharing projects

Once you are finished adding content to a project, you can share it.

* To share the project with your colleagues, go to **[!UICONTROL Share > Share Project]**. Recipients are other users in your organization who have Adobe Analytics accounts.
* To share your project via a link, go to **[!UICONTROL Share > Get Project Link]**. Note that this still requires a login to Adobe Analytics within your organization.

### Exporting projects

In addition to PDF, [!UICONTROL Analysis Workspace] offers a CSV export.

1. Click *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, which opens a modal window.
2. Specify the file type and recipients.
3. Click [!UICONTROL Send Now].

## Custom Reports

When creating a custom report in Google Analytics, the fields required are similar to the workflow in building out a visualization in workspace. Dimensions, Metrics, and Filter definitions are similar between platforms. In Analysis Workspace, instead of selecting dimensions and metrics from a list, dimensions and metrics are dragged onto a freeform table.

### Calculated metrics in custom reports

Custom reports is one of the few areas in Google Analytics that allows the use of calculated metrics. Because Analysis Workspace operates like a canvas, calculated metrics work retroactively and in any context.

To create a calculated metric:

1. Click the **+** icon near the metric list to open the [!UICONTROL Calculated Metric Builder].
2. Give your calculated metric a name and specify a format.
3. Drag metric components to into the definition area, and use the drop-down lists between each component to designate an operator.
4. Once the calculated metric contains the desired formula, click Save to go back to your workspace.
5. Drag the newly defined calculated metric onto the workspace.

    Learn more about [Calculated Metrics](/help/components/c-calcmetrics/cm-overview.md) in the Components user guide.

## Custom Alerts

Alerts are available on both platforms. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. See [Intelligent Alerts](/help/components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
