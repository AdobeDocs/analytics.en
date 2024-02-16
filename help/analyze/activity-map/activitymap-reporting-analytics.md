---
description: Describes how to set permissions and which dimensions are available in Analytics.
title: Activity Map reporting in Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
---
# Activity Map reporting in Analytics

Describes how to set permissions and which dimensions are available in Analytics.

## Set permissions {#permissions}

Before users can report on Activity Map dimensions, you as the Admin need to

* [Add users to the Activity Map Access product profile](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Customize user access to dimensions. See the section below.

## Analytics Activity Map dimensions {#dimensions}

You can [customize user access to dimensions](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) at a granular level. Here are the Activity Map dimensions available in Analytics:

|  Dimension  | Description  |
|---|---|
|  Activity Map Page  | Lists the pages on which a link was clicked.  |
|  Activity Map Region  | Lists all collected link regions across the whole web site. Note that if a region appears on multiple pages, the metric will be aggregated across all its pages.  |
|  Activity Map Links  | Lists all collected links across the whole web site.  |
|  Activity Map Links & Region  | Lists all collected links with their region across the whole web site.  |
|  Activity Map XY  | Unused  |

* These dimensions should be available in Analysis Workspace and Report Builder, provided that your Analytics implementation is [enabled for Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* In Analysis Workspace, pull the Activitymap-related dimensions into a report.
* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired Activity Map page into the Activity Map Links & Region.
