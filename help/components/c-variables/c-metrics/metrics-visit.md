---
description: A sequence of page views in a sitting. The visits metric is commonly used in reports that display the number of user sessions within the selected time period.
keywords: visit
solution: Analytics
title: Visit
topic: Metrics
uuid: 91317487-f116-4546-8cd2-421418c49a7a
---

# Visit

A sequence of page views in a sitting. The visits metric is commonly used in reports that display the number of user sessions within the selected time period.

> [!NOTE] For information about how visits and mobile app launches are calculated, see [Compare Visits and Mobile App Launches](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) in the Knowledge Base.

The visit metric is always associated with a time period, so you know whether to count a new visit if the same visitor returns to your site. A session starts when the user first arrives on your site, and ends under one of the following scenarios:

* **30 minutes of inactivity:** Almost all sessions end in this manner. If more than 30 minutes has lapsed between image requests, a new visit begins.
* **12 hours of consistent activity:** If a user fires images requests without a 30+ minute gap for 12 hours, a new visit automatically starts.
* **2500 hits:** If a user generates a large number of hits without starting a new session, a new visit is counted after 2500 image requests.
* **100 hits in 100 seconds**: If a visit consists of more than 100 hits that occur in fewer than 100 seconds, the visit automatically ends. This behavior typically indicates bot activity, and this limitation is enforced to prevent these processing-intensive visits from increasing latency and increasing the time it takes to generate reports.

> [!NOTE] The definition of a visit can be shortened for a report suite if specifically requested, but it cannot be lengthened. Have one of your organization's supported users contact Customer Care to request this change.

The following scenarios do not start a new visit:

* The user closing the tab, reopening it, and navigating back to your site within 30 minutes. The user can also close his browser or reboot the computer and still be counted as a single visit (given the visitor returns to your site within the 30-minute time period).
* Users browsing your site in multiple tabs. Though multi-tabbed browsing does not increment visits or visitors, using a separate browser does. This is because the different tabs reference the same cookies, while separate browsers do not.

A visit does not necessarily coincide with a browser session. For example, if a visitor closes the browser, reopens the browser, and comes to your site five minutes later, it is recognized as a continuation of the same visit. This also means that if a visitor remains on one page for 35 minutes, the visit will have closed and processed, and a new visit will start if they click through to another page.

When a visit ends, all variables with a visit expiration are expired and no longer persist. The visit number metric will be incremented on the next visit for this visitor.

> [!NOTE] If you are using Analytics as the reporting source for Adobe Target, refer to [Minimizing Inflated Visit and Visitor Counts in A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) in the [!DNL Target] documentation.

For more information, refer to [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html) in the Adobe Analytics Implementation guide.

**Time Periods**

A visit is reported in each time period in which activity occurred. For example, suppose that a visit begins at 11:45 p.m. on December 1st, and continues until 12:30 a.m. on December 2nd. The visit is counted on December 1st and December 2. This reporting applies to other time periods, including weekly, monthly, quarterly, and yearly.
