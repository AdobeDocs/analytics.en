---
title: Multiple Report Suites
description: Learn how to work with multiple report suites in one Analysis Workspace project.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
---
# Multiple report suites

You can create projects in Analysis Workspace with data from more than one report suite. Report suites are chosen at the panel level, so you can choose a different report suite for each panel within the same Workspace project. 

This capability is useful if you want to:

* Compare data from two different regions, and the data resides in two different report suites. You can build tables and visualizations to compare the data side by side.

* Build a dashboard of metrics and visualizations to report out to other organizations. You can pull data from various report suites into in the same project.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Multiple report suites](https://video.tv.adobe.com/v/32843?quality=12&learn=on){target="_blank"} for a demo video.

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
    * Where a calculated metric will be created: [Calculated metric builder](/help/components/calculated-metrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).
    * Where an alert will be built: [Alert builder](/help/components/alerts/alert-builder.md).
