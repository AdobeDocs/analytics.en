---
title: Accounts and report suites
description: Learn to use a login company and a report suite to keep data silos organized in Adobe Analytics.
feature: Third-party Integration
exl-id: f4cf2a77-30c1-40f8-ba18-e4d71e170831
TQID: https://experienceleague.adobe.com/0ESd9J7cUvnOBqDRM3HqkPkebqmnFVHDQV-2sQsc08w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Accounts and report suites

In Adobe Analytics, there are two levels to keep data silos organized:

* A **login company** is an overarching organization that contains one or more report suites. A login company is comparatively similar to an *account* in other Analytics tools, such as Google Analytics. Consultants who work with several organizations would typically have access to multiple login companies.
* A **report suite** is a repository where you send data and where you pull reports. A report suite typically contains data from one website, but that is to the discretion of each organization's implementation. A report suite is comparatively similar to a *View* in other analytics tools.

Larger organizations usually have multiple report suites, one for each site or app. Check with an admin within your organization if you are unsure which report suite you should be using to obtain data.

One key difference between Adobe's data collection method and many other tools is that you specify which report suite(s) to send data to within your implementation. This is different from other tools that typically send all your data to one collection location, then filter that down to views or profiles.

[!UICONTROL Virtual report suites] are also available in Adobe Analytics, which provides a filtered view of a report suite without altering data collection or historical data. For example, you can use a [!UICONTROL virtual report suite] to eliminate bot traffic not previously caught, or exclude fraudulent/outlier revenue. See [Virtual report suites](/help/components/vrs/vrs-about.md) in the Components user guide for more information.
