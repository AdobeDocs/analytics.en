---
description: Describes how to set permissions and which dimensions are available in Analytics.
title: Activity Map reporting in Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
---
# Activity Map reporting in Analytics

Describes how to set permissions and which dimensions are available in Analytics.

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on Activity Map dimensions, you as the Admin need to

* [Add users to the Activity Map Access Group](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Add report suites you would like to have access to this group. Navigate to **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**.
* Customize user access to dimensions. See the section below.

## Analytics Activity Map dimensions {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

You can [customize user access to dimensions](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) at a granular level. Here are the Activity Map dimensions available in Analytics:

|  Dimension  | Description  |
|---|---|
|  Activity Map Page  | Lists the pages on which a link was clicked.  |
|  Activity Map Region  | Lists all collected link regions across the whole web site. Note that if a region appears on multiple pages, the metric will be aggregated across all its pages.  |
|  Activity Map Links  | Lists all collected links across the whole web site.  |
|  Activity Map Links & Region  | Lists all collected links with their region across the whole web site.  |
|  Activity Map XY  | Unused  |

* These dimensions should be available in Analysis Workspace, Reports & Analytics, and Report Builder, provided that your Analytics implementation is [enabled for Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports & Analytics, navigate to **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired Activity Map page into the Activity Map Links & Region.
