---
title: Visits
description: A sequence of page views in a sitting.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
---
# Visits

The 'Visits' metric shows the number of sessions across all visitors on your site.

## How this metric is calculated

A visit always ties to a time period, so you know whether to count a new visit if the same person returns to your site. A visit starts when the user first arrives on your site. A visit ends when they meet any of the following criteria:

* **30 minutes of inactivity**: Almost all sessions end in this manner. If more than 30 minutes lapse between hits, a new visit begins.
* **12 hours of activity**: If a user consistently fires image requests without any 30-minute gaps for more than 12 hours, a new visit automatically starts.
* **2500 hits**: If a user generates a large number of hits without starting a new session, a new visit is counted after 2500 image requests.
* **100 hits in 100 seconds**: If a visit consists of more than 100 hits that occur in fewer than 100 seconds, the visit automatically ends. This behavior typically indicates bot activity, and this limitation is enforced to help increase report performance.

A visit does not necessarily coincide with a browser session because of the above criteria. One of the most common differences is where a visitor navigates to your site, leaves the tab open for more than 30 minutes, then resumes browsing. While this action is technically part of the same browsing session, Adobe considers this action two separate visits.

## Behavior that affects visits

If a visitor performs any of these actions, a new visit starts:

* Clears their cache mid-session and continues browsing your site
* Leaves your site open in a tab for longer than 30 minutes, then continues browsing
* Opens a different browser and navigates to your site on the same computer
* The same person browsing your site on different devices

If a visitor performs any of these actions, a new visit does **not** start as long as there is less than 30 minutes between consecutive hits:

* Closes their browser, then navigates to your site again
* Restarts their computer, opens the same browser, and navigates to your site again
* Transitions to a different network, such as disconnecting from a wired network docking station to a wireless network
* Browses your site in multiple tabs. If a visitor switches back and forth between tabs, each hit counts as part of the same visit.

## Change the definition of a visit

You can change the definition of a visit to a time other than 30 minutes.

* For [Virtual report suites](../vrs/vrs-about.md), you can change the visit timeout using the [!UICONTROL Visit timeout] dropdown. You can change visit timeout to any reasonable value.
* For standard report suites, contact Customer Care to request visit length be shortened for a given report suite. Visit length for standard report suites cannot exceed 30 minutes, so you can only shorten it.

## Visits that span a date boundary

A visit counts for each time period involved. For example, if you have a visitor that starts navigating your site on Monday at 11:45 PM, then sends their last image request on Tuesday at 12:10 AM, you would see a visit attributed to both Monday and Tuesday. However, the total visit metric is deduplicated, showing a single visit for the project date range.

## Visits on a dimension versus total visits

Visits in context of a dimension (for example, [Marketing channel](../dimensions/marketing-channel.md)) show the number of visits that contained a particular dimension item at any time. Multiple dimension items frequently exist on different hits in the same visit. Attempting to sum visits that report on dimension items usually does not make sense.

## Visits All Visitors in Data Warehouse

The metric 'Visits - All Visitors' is available in Data Warehouse in addition to the 'Visits' metric. The 'Visits - All Visitors' metric is comparable to the 'Visits' metric in other Analytics tools. The 'Visits' metric in Data Warehouse excludes visitors that don't have persistent cookies. Adobe recommends using 'Visits - All Visitors' in Data Warehouse requests where visits are desired as a metric.
