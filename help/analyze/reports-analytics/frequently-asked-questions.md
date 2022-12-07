---
description: Provides answers and troubleshooting suggestions to some of the most frequently asked Analytics questions.
keywords: Troubleshooting Analytics
title: Frequently Asked Questions for Reports & Analytics
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
---
# Frequently Asked Questions

{{ra-eol}}

Provides answers and troubleshooting suggestions to some of the most frequently asked Analytics questions for Reports & Analytics. For frequently asked implementation questions, see the [FAQ](/help/implement/faq.md) in the Implement user guide.

+++My account has been locked; how do I unlock it?
To reactivate an account, contact an admin within your organization. See also [Troubleshoot login issues with Adobe Analytics](/help/technotes/troubleshoot-login.md) in the Technotes user guide.
+++

+++Why do I see a blank report even though I know data is collected?
There are several things to check to troubleshoot report data:

* Check the metrics used: Some reports default to Revenue in Reports & Analytics. Make sure the metric you're viewing is relevant to the report.
* Check the date range: Date ranges, especially those beyond your organization's data retention policy, can return no data. Check to make sure that your date range is set correctly.
* Check internal URL filters: Some traffic sources reports do not work until after you correctly define internal URL filters.
+++

+++Why are some reports missing in the navigation menu?
Any reports missing from a menu most commonly originate from either restricted permissions or menu customization. Contact a product admin within your organization to ensure you have access to all the dimensions and metrics needed, and that a report suite's menu structure has not be customized.
+++

+++Why are some long values cut off?
Almost all variables in Adobe Analytics have a character limit. Page Name has a 100 character limit, while custom conversion variables (eVars) have a 255 character limit. Adobe recommends making sure that values you send to Adobe are concise to prevent truncation.
+++

+++Why do I see a major delay in reporting?
Real-time reporting allows some traffic metrics to be available within minutes, while conversion and other processing-intensive data is usually available within 30-90 minutes. Though the Experience Cloud platform is robust, there are a few situations that may lead to delays in reporting. This delay is referred to as latency. See [Latency](/help/technotes/latency.md) in the Technotes user guide for more information.
+++

+++Why can't I see the device version on iPhones?
Apple devices report their firmware version in the user agent string, not the device version. It is difficult to determine iPhone device version using information available to Adobe Analytics. See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.
+++

+++Why do totals at the bottom of my report not match when I sum the values?
Dimension items can often apply in multiple places; for example, visits that span midnight or multiple products belonging to a single order. The dimension item is reported across all applicable line items, but is deduplicated in the report's total. See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.
+++

+++How do I exclude data from a particular IP addresses in my report suite?
You can eliminate data from internal website activities, such as site testing and employee usage, from your reports. This feature allows you and your colleagues to visit your site without skewing your traffic data. See [Exclude by IP Address](/help/admin/admin/exclude-ip.md) in the Admin user guide for more information. 
+++

+++Can I delete a report suite?
Deleting a report suite is not possible. However, a report suite can be hidden from all views in Adobe Analytics. Note that server calls sent to a hidden report suite still count towards your monthly contract limit. See [Hide report suites](help/admin/admin/get-started/company/c-hide-report-suites.md) in the Admin user guide for more information.
+++

+++When using segmentation, what container should I use? Page view, visit, or visitor?
The segment container you use is depending on how broad you want to capture data. Page view containers only bring in hits that match segment criteria, useful for filtering out irrelevant parts of visits. Visit containers bring it all hits of a visit where one or more hits matched segment criteria, useful for looking at sessions in general. Visitor containers bring in all visits where a hit matched segment criteria, useful for looking at people. It is your choice as an analyst to determine what segment container is best to use. See [Segmentation overview](/help/components/segmentation/seg-overview.md) in the Components user guide for more information.
+++

+++Why isn't my segment showing up in Data Warehouse?
Due to Data Warehouse's unique processing architecture, the platform is not optimized to handle some types of data, such as pathing. See [Data Warehouse segment compatibility](/help/components/segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
+++
