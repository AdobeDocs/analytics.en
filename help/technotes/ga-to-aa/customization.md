---
title: Report Customization in Adobe Analytics
description: Learn how to customize reports in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
TQID: https://experienceleague.adobe.com/vvVKR7JKV12zgIic0rso4OihH5kyAoZBV983R3VmOic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
    internal-label: Custom reports
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
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

    Learn more about [Calculated Metrics](/help/components/calculated-metrics/cm-overview.md) in the Components user guide.

## Custom Alerts

Alerts are available on both platforms. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. See [Alerts overview](/help/components/alerts/alerts-overview.md) in the Components User Guide for more information.
