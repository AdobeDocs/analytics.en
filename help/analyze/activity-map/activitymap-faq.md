---
description: Frequently asked questions for setting up, configuring, and employing features in Activity Map.
title: Activity Map FAQ
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
---
# Activity Map FAQ

Frequently asked questions for setting up, configuring, and employing features in Activity Map.

## Do all Analytics customers have access to the Admin Tools ActivityMap Enablement page?

Organizations with a contract for Adobe Analytics Standard, Premium, and Ultimate have access to Activity Map.

## How does Activity Map support Single-Page Applications (SPA)?

Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the Links On Page table's Present column for that link updates with [!UICONTROL Displayed] or [!UICONTROL Hidden].

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the [!UICONTROL Links On Page] table. Activity Map sends a new data request that includes these new links. The new links should appear in the [!UICONTROL Links On Page] table when the data request is handled by the UI.


## Does Activity Map provide data on "views"?

No, Adobe does not track links that were viewed.

## What browsers and versions does Activity Map support?

Activity Map supports the latest version of most modern browsers.

## Does Activity Map increase server calls?

Activity Map does not send server calls by itself. Instead, Activity Map context data variables are included with Analytics page view calls on the subsequent page.

## Why are some ranked item overlays missing?**

Some ranked links, such as submenu links, are hidden from the page. As a consequence, their corresponding link overlays are not shown. Rank is computed for all links on the page, including hidden links.

## How is link ranking determined in the All Links report?**

* **In Gradient and Bubble mode**: Rank is determined by the metric column. For links with same metric value, the rank is further based on link ID alphabetical order.
* **In Gainer & Loser mode**: Rank is primarily determined by the % Gain column. For links with the same gain, the rank is further based on the link ID alphabetical order.

## How does Activity Map work with pages that use multiple report suites?

By default, Activity Map uses the report suite that is associated with the first tag that is sent by the page. You can select a different tagged report suite through the **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]** tab.

## How long does Activity Map scan for Adobe Analytics on the page?

Activity map scans for the presence of Adobe Analytics for up to 20 seconds after a page complete event.

## How does Activity Map handle dynamic content?

Activity Map checks every 2 seconds to see if it has found changes in the state of the web page such as:

*   HTML content that has become visible
*   HTML content that is hidden
*   New HTML content that was injected

If content is hidden or shown, the application automatically changes the affected links state (and therefore overlays) from hidden to shown or from shown to hidden. If new content is injected, the application retrieves the associated links, pull analytics data for them, and adds overlays for these links.

## What metric is the Page Flow report based on?

All data shown is based on page views.

## Can I export Activity Map context data variables through data feeds?

Activity map context data variables are not available in data feeds.

## Do segments work in Live mode?

No, segments do not work in Live mode. The functionality is equivalent to that of real-time reporting in Reports & Analytics, which do not support segmentation.

## Is Activity Map compatible with virtual report suites?

Yes. However, due to virtual report suite limitations, Activity Map's Live Mode is not compatible with virtual report suites.
