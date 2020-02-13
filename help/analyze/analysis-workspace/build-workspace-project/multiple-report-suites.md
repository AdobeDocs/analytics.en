---
title: Multiple report suites in Workspace
description: Learn how and why to create projects in Workspace with multiple report suites
---

# Multiple report suites in Workspace

>[!IMPORTANT]
>Multiple report suites in Workspace is currently in limited release.

You can now create projects in Analysis Workspace with data from more than one report suite. Report suites are now chosen at the panel level, so you can choose a different report suite for each panel within the same Workspace project. 

This capability is useful if you want to, for example,

* Compare data from two different regions, and the data resides in two different report suites. You can build tables and visualizations to compare the data side by side.

* Build a dashboard of metrics and visualizations to report out to other organizations. You can now pull data from various report suites into in the same project.

## Active panel

We are introducing the concept of "active panel" versus "inactive panel" with this feature. The active panel is recognizable by the light blue border around it. Simply clicking inside a panel makes that panel the active panel.

>[!IMPORTANT]
>You can drag and drop components **only into the active panel**, even if other panels have the same report suite. If you want to change the panel while dragging and dropping, you can use a short cut: press `shift` while dragging to change an inactive panel to an active panel.

|Task|Active panel|Inactive panel|
|---|---|---|
|Change report suite|Yes|No|
|Drag and drop components|Yes|No|
|Drag and drop visualizations|Yes|No|

## Work with multiple report suites

![](assets/mrs-ui.png)

1. Create a new project with 2 or more panels in Workspace.

1. Drag and drop components (metrics, dimensions, segments, date ranges) into the panel. Ensure panels have data and visualizations that are specific to their report suite.


    >[!NOTE]
    >Sometimes, an "Incompatible Report Suite" message shows up when loading a project (or switching to a report suite) where not all of the components included in the project are included in the report suite. The missing components will be listed. Follow [these instructions](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles) to set permissions to the required metrics/dimensions.

    ![](assets/incompat-rs.png)

    You have 3 options to deal with this incompatibility:
    * Continue with some missing components. This will result in no data for those components, and/or blank visualizations.
    * Undo.
    * Change the report suite.

1. Change the panel to a different report suite and notice how the component label (currently active report suite) and listed components are updating based on the new report suite.

1. Use the keyboard shortcut (`shift` while dragging) to turn an inactive panel to an active panel.

1. (Optional) You can also go to other Analytics component builders and ensure that they now show a report suite label indicating

    * Where a segment will be created: [Segment Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).
    * Where a calculated metric will be created: [Calculated Metric Builder](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).
    * Where an alert will be built: [Alert Builder](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html).