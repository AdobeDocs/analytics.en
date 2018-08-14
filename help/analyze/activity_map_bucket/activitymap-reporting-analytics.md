---
description: Describes how to set permissions and which dimensions are available in Analytics.
seo-description: Describes how to set permissions and which dimensions are available in Analytics.
seo-title: Activity Map reporting in Analytics
solution: Analytics
title: Activity Map reporting in Analytics
topic: Activity map
uuid: 45a6a5b8-9ad8-4b8a-bb2a-1318fbcd6ae2
index: y
internal: n
snippet: y
translate: y
---

# Activity Map reporting in Analytics


## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on Activity Map dimensions, you as the Admin need to 



* [ Add users to the Activity Map Access Group ](activitymap-enable.md#section_4C7A47BB7DEF4AFFBC276392467F9675).
* Add report suites you would like to have access to this group. Navigate to  **[!UICONTROL  Admin]** > **[!UICONTROL  User Management]** > **[!UICONTROL  Groups]** > **[!UICONTROL  Activity Map Access]** > **[!UICONTROL  Edit]** .
* Customize user access to dimensions. See the section below.

## Analytics Activity Map dimensions {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

You can [ customize user access to dimensions ](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) at a granular level. Here are the Activity Map dimensions available in Analytics: 



|  Dimension  | Description  |
|---|---|
|  Activity Map Page  | Lists the pages on which a link was clicked.  |
|  Activity Map Region  | Lists all collected link regions across the whole web site. Note that if a region appears on multiple pages, the metric will be aggregated across all its pages.  |
|  Activity Map Links  | Lists all collected links across the whole web site.  |
|  Activity Map Links &amp;amp; Region  | Lists all collected links with their region across the whole web site.  |
|  Activity Map XY  | Unused  |



* These dimensions should be available in Analysis Workspace, Reports &amp; Analytics, and Report Builder, provided that your Analytics implementation is [ enabled for Activity Map ](activitymap-enable.md#concept_4C5A1178C8E040B99CAE7A25473E67D6).
* In Reports &amp; Analytics, navigate to **[!UICONTROL  View All Reports]** > **[!UICONTROL  Activity Map]**.
* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired Activity Map page into the Activity Map Links &amp;amp; Region.
