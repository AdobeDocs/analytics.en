---
description: Enable dimensions so that Activity Map can collect data.
title: Activity Map Reporting
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
---
# Activity Map Reporting

Allows you to enable dimensions for use with [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]**

This section of the documentation focuses on enabling dimensions that Activity Map uses. See [Activity Map overview](/help/analyze/activity-map/overview.md) for more information about the overlay, implementation variables, and dimensions.

When you select the **[!UICONTROL Enable Activity Map Reports]** button, the following dimensions are created:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md): The link name that was clicked.
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md): The region name that was clicked.
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md): The page name at the time that the link was clicked.
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md): A concatenated value of Activity Map Link and Activity Map Region.

Once enabled, your implementation can begin sending data to these dimensions for use in [Analysis Workspace](/help/analyze/analysis-workspace/home.md) and the [Browser extension overlay](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>When you enable Activity Map for a report suite, it is permanently enabled without any way to disable it in the future.
