---
title: Accounts and report suites
description: Learn to use a login company and a report suite to keep data silos organized in Adobe Analytics.
feature: Third-party Integration
exl-id: f4cf2a77-30c1-40f8-ba18-e4d71e170831
---
# Accounts and report suites

In Adobe Analytics, there are two levels to keep data silos organized:

* A **login company** is an overarching organization that contains one or more report suites. A login company is comparatively similar to an *account* in other Analytics tools, such as Google Analytics. Consultants who work with several organizations would typically have access to multiple login companies.
* A **report suite** is a repository where you send data and where you pull reports. A report suite typically contains data from one website, but that is to the discretion of each organization's implementation. A report suite is comparatively similar to a *View* in other analytics tools.

Larger organizations usually have multiple report suites, one for each site or app. Check with an admin within your organization if you are unsure which report suite you should be using to obtain data.

One key difference between Adobe's data collection method and many other tools is that you specify which report suite(s) to send data to within your implementation. This is different from other tools that typically send all your data to one collection location, then filter that down to views or profiles.

[!UICONTROL Virtual report suites] are also available in Adobe Analytics, which provides a filtered view of a report suite without altering data collection or historical data. For example, you can use a [!UICONTROL virtual report suite] to eliminate bot traffic not previously caught, or exclude fraudulent/outlier revenue. See [Virtual report suites](/help/components/vrs/vrs-about.md) in the Components user guide for more information.
