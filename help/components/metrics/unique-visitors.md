---
title: Unique visitors
description: The number of unique visitor IDs.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
---
# Unique visitors

The 'Unique visitors' metric shows the number of visitor IDs for the dimension item. It is one of the most common metrics used when determining traffic, as it gives a high-level overview of the popularity of a dimension item. For example, a visitor can come to your site every day for a month, but they still count as a single unique visitor.

If you use [Cross-device analytics](../cda/overview.md), this metric is replaced with the [Unique devices](unique-devices.md) metric.

## Daily, weekly, monthly, quarterly, and yearly unique visitors

Reports & Analytics provides options for daily, weekly, monthly, quarterly, and yearly unique visitors. Instead of counting a single unique visitor for the entire time period, unique visitors count based on the selected metric. For example, you want to look at daily unique visitors for your site. If a visitor comes to your site in the morning and again at night, they count as a single daily unique visitor. If a visitor comes to your site on Monday and again on Tuesday, they count as two daily unique visitors.

Analysis Workspace treats unique visitors based on the granularity of the report. For example, if you use the [Day](../dimensions/day.md) dimension, you'll see daily unique visitors for each dimension item. However, for the report total, it is deduplicated unique visitors for the freeform table's date range.

## How this metric is calculated

This metric counts the number of unique visitor ID's for a given dimension item. It uses multiple advanced mechanisms to identify unique visitors, since there are several ways to identify them. The following table lists the ways a visitor is identified, along with its priority. Some hits can have multiple visitor identification methods; in these cases the higher priority method is used.

| Order Used | Query Parameter (collection method) | Present When |
| --- | --- | --- |
| 1 | `vid` | The [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable is set. |
| 2 | `aid` | Visitor has an existing [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Set on implementations without or prior to implementing the Visitor ID service. |
| 3 | `mid` | Visitor has an existing [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Set on implementations using the [Adobe Experience Cloud Identity service](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| 4 | `fid` | Visitor has an existing [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie, or if `aid` and `mid` could not be set for any reason. |
| 5 | IP Address, User Agent, Gateway IP Address | Last resort to identify a unique visitor if the visitor's browser does not accept cookies. |

>[!NOTE]
>
>Each Analytics visitor ID is tied to a profile on Adobe's servers. These visitor profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.

## Behavior that affects unique visitor count

Unique visitor identifiers are typically stored in a browser cookie. A new unique visitor is counted if they perform any of the following:

* Clears their cache at any time
* Opens a different browser on the same computer. One unique visitor is counted per browser.
* The same person browsing your site on different devices. A separate unique visitor is counted per device. You can use [Cross-device analytics](../cda/overview.md) to combine visitors together using the [People](people.md) metric.
* Opens a private browsing session (such as Chrome's Incognito tab).

A new unique visitor is *not* counted, as long as the cookie identifier is preserved:

* Closes their browser for an extended period
* Upgrades their browser to the latest version
