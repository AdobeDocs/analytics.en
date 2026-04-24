---
title: Multiple Report Suites
description: Learn how to work with multiple report suites in one Analysis Workspace project.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
TQID: https://experienceleague.adobe.com/IrWsvooPWqWmbDAD-70CgI71gEPJCQY-1wFHFyuJsyc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
    internal-label: Segment Builder
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Multiple report suites

You can create projects in Analysis Workspace with data from more than one report suite. Report suites are chosen at the panel level, so you can choose a different report suite for each panel within the same Workspace project. 

This capability is useful if you want to:

* Compare data from two different regions, and the data resides in two different report suites. You can build tables and visualizations to compare the data side by side.

* Build a dashboard of metrics and visualizations to report out to other organizations. You can pull data from various report suites into in the same project.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Multiple report suites](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Apply report suite to all panels

You can apply a report suite to all panels at once by right-clicking any panel header and selecting **[!UICONTROL Apply Report Suite to All Panels]**.

![](assets/apply-rs-all-panels.png)

## Active panel

You can recognize the active panel by the light blue border around it. Simply select inside a panel to turn that panel into the active panel.

>[!TIP]
>
>You can drag and drop to any panel that is in the same report suite as your active panel. By dragging into an inactive panel of the same report suite, the panel will become active.
>

## Work with multiple report suites

![](assets/mrs-ui.png)

1. Create a new project with 2 or more panels in Workspace.

1. Drag and drop components (metrics, dimensions, segments, date ranges) into the panel. Ensure panels have data and visualizations that are specific to their report suite.


    >[!NOTE]
    >
    >Sometimes, a banner displays when loading a project (or switching to a report suite) where not all of the components included in the project are included in the report suite. The missing components will be listed. Follow [these instructions](/help/admin/admin-console/permissions/product-profile.md) to set permissions to the required metrics/dimensions.
    >

    ![](assets/incompat-rs.png)

    You have 3 options to deal with this incompatibility:
    * Enable the required dimensions/metrics
    * Change the report suite.
    * Continue with some missing components. This will result in no data for those components, and/or blank visualizations.

1. Change the panel to a different report suite and notice how the component label (currently active report suite) and listed components are updating based on the new report suite.

1. Use a keyboard shortcut (`shift` while dragging) to turn an inactive panel to an active panel.

1. (Optional) You can also go to other Analytics component builders and ensure that they now show a report suite label indicating

    * Where a segment will be created: [Segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md).
    * Where a calculated metric will be created: [Calculated metric builder](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md).
    * Where an alert will be built: [Alert builder](/help/components/alerts/alert-builder.md).
