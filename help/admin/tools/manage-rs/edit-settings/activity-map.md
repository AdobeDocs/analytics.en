---
description: Enable dimensions so that Activity Map can collect data.
title: Activity Map Reporting
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
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
