---
description: Frequently asked questions for setting up, configuring, and employing features in Activity Map.
title: Activity Map FAQ
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
---

# Activity Map FAQ

Frequently asked questions for setting up, configuring, and employing features in Activity Map.

## Implementation and AppMeasurement

**Q: What are the implementation steps for enabling the new Activity Map?**

A: Please review [Enable Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**Q: Do all Analytics customers have access to the Admin Tools ActivityMap Enablement page?**

A: Adobe SiteCatalyst customers do not have access to the Admin Console's Activity Map Enablement page. Only companies under Adobe Analytics Standard and Adobe Analytics Premium contract have access to this configuration page.

**Q: Can the new AppMeasurement code be configured through Dynamic Tag Management (DTM)?**

A: Yes, you can [manually implement](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) the new AppMeasurement code.

**Q: What are the big changes in the AppMeasurement v1.6 library?**

A: The only change in AppMeasurement v1.6 is in the Activity Map link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**Q: Will AppMeasurement be rolled out at the domain level rather than on specific pages?**

A: AppMeasurement is rolled out at the report-suite level. The report-suite level is typically associated with a domain level, but this differs with each implementation.

**Q: DTM automatically loads an older version (1.3.4) of the Visitor API than Activity Map wants (1.5.1). Is this a problem?**

A: No. Activity Map functionality is not dependent on the VisitorAPI.

## Activity Map application

**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.

**Q: Does Activity Map provide data on “views”?**

A: No, tracking all the links that are viewed on each page load would require us to collect a lot more data. As a free add-on, Activity Map does not provide this functionality.

**Q: Can I use Activity Map if I did not previously use Visitor ClickMap on my website?**

A: Having the legacy version - now simply called ClickMap - installed is not a prerequisite for implementing the new version. Adobe will continue to support the legacy version for a limited period of time.

**Q: What browsers and versions are supported by Activity Map?**

A: We support the latest version of the four main browsers (Chrome, Firefox, Safari and IE).

**Q: What are the default Overlay Settings?**

A: By default, Activity Map shows ALL links that have collected data.

When popup panels are shown on top of customer web pages, overlays belonging to links that are located below the popup panel may be shown on top of the popup panel.

**Q: Why are some ranked item overlays missing?**

A: Some ranked links may be hidden from the page (submenu links, for example). As a consequence, their corresponding link overlays will not be shown. So you can expect to see overlay rankings that are missing some specific rank values, because the rank is computed to for all links in the page (the present one + the hidden ones).

**Q: How is link ranking determined in the All Links report?**

*   In **Gradient** and **Bubble** mode: Ranking is determined by the metric column. For links with same metric value, the rank is further based on link ID alphabetical order.
*   In **Gainer & Loser** mode, rank is primarily determined by the % Gain column. For links with the same Gain, the rank is further based on the link ID alphabetical order.

**Q: Why is link click data not collected when Activity Map is running?**

A: While Activity Map is in use, link click data is not collected by the Analytics tag. This behavior follows the behavior of the ClickMap plug-in.

**Q: How does the Activity Map All Links Report compare with Reports & Analytics Activity Map reporting?**

A: To pull the All Links Report in Activity Map, we create a breakdown request as follows: Activity Map Page = "visitedpage", broken down by Activity Map Link&Region in `<list of link&regions present in the page at rendering time>`.

To get an equivalent report in Reports & Analytics, you would need to first navigate to the Activity Map Page report. There, you would filter for the visited pagename in Activity Map. The visited Pagename is shown in the left column in the Activity Map Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose Activity Map Links & Regions as a secondary dimension.

However, it is important to note that the obtained report in R&A will list all Links & Regions that were collected for that Page. But Activity Map only reports on Links&Regions that are currently present in the webpage. So if you have a news site, it will only show data for the news story present at this time, and not the news stories that were present earlier in the day.

**Q: How does Activity Map work with pages containing multiple tags listing multiple report suites?**

A: By default, Activity Map uses the report suite that is associated with the first tag that is sent by the page. You can select a different tagged report suite through the Activity Map Settings > Others tab.

**Q: For how long does Activity Map scan for the Analytics Tag?**

A: We scan for the Analytics tag for up to 20 seconds after a page complete event.

**Q: How does Activity Map handle dynamic content?**

A: Activity Map checks every 2 seconds to see if it has found changes in the state of the web page such as:

*   HTML content that has become visible
*   HTML content that is hidden
*   New HTML content that was injected

If content is hidden or shown, the application automatically changes the affected links state (and therefore overlays) from hidden to shown or from shown to hidden.

If new content is injected, the application will retrieve the associated links, pull analytics data for them, and add overlays for these links.

**Q: What metric is the Page Flow report based on?**

A: All data shown is based on page views.

**Q: Can you explain Activity Map behavior with various type of pages?**

*Web page without Analytics tag*

A warning message is shown below toolbar indicating that no tag is present.

*Web page with incompatible Analytics Tag (AppMeasurement v1.5 or earlier)*

A warning message is shown indicating that you need to upgrade the page code to v1.6 or more.

*Web page with compatible Analytics Tag (AppMeasurement v1.6 or later), but Activity Map reporting was not enabled in Admin Tools*

A warning message is shown indicating that you need to ask your Admin to \[Enable the Activity Map report\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md") .

**Q: Can I export Activity Map data (contextData) via [Analytics Data Feed](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)?**

A: No.

## Segmentation in Activity Map

**Q: Are segments tied to the individual user segments? Are shared segments available in Activity Map?**

A: Activity Map inherits your reporting segments from Analytics.

**Q: Do segments work in Live mode?**

A: No, segments do not work in Live mode. The functionality is equivalent to that of real-time reporting in Reports & Analytics.

## Virtual report suites

**Q: Is Activity Map compatible with virtual report suites?**

A: Yes. However, due to virtual report suite limitations, Activity Map's Live Mode is not compatible with virtual report suites.
