---
title: Visitor identification in Adobe Analytics
description: Learn how to identify visitors in Adobe Analytics using the latest best practices.
---
# Visitor identification in Adobe Analytics

Visitor identification is central to the value that Adobe Analytics provides for understanding online user behavior. It involves linking hits to the same person over time using a common identifier. Accurate visitor identification ensures reliable metrics and supports a healthy implementation strategy. Adobe recommends that organizations prioritize modern identity services for consistency and data integrity across platforms.

Visitor identification in Adobe Analytics consists of the following components:

* Client-side identifier: Typically stored in a first-party cookie. Implementations that rely on third-party cookies are less consistent with visitor identification due to modern browser privacy standards.
* Server-side identifier: Each Analytics visitor ID is tied to a profile on Adobe's servers. These visitor profiles are what allow persistence on variables such as [eVars](/help/components/dimensions/evar.md). Profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.

## Adobe Analytics identification order of operations

When Adobe receives a hit, the following checks are made in order. If a given property is present, Adobe uses that identifier for the hit. If multiple identifiers are present in a hit, only the first method is used.

| Order used | Query parameter | Present when |
|---|---|---|
| **1<sup>st</sup>** | `vid` | The [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable is set. |
| **2<sup>nd</sup>** | `aid` | The visitor has an existing [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. Set on implementations without or prior to implementing the Visitor ID service. |
| **3<sup>rd</sup>** | `mid` | The visitor has an existing [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. Set on implementations using the [Adobe Experience Cloud Identity service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Adobe recommends using the ID service for all implementations where possible. |
| **4<sup>th</sup>** | `fid` | The visitor has an existing [`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie, or if `aid` and `mid` could not be set for any reason. |
| **5<sup>th</sup>** | IP Address, User Agent, Gateway IP Address | Used as a last resort to identify a unique visitor if the visitor's browser does not accept cookies. |

## Behavior that affects unique visitor count

Unique visitor identifiers are typically stored in a browser cookie. A new unique visitor is counted if a visitor performs any of the following actions:

* Clears their cookies at any time. One unique visitor is counted for a hit after each time their cache is cleared.
* Visitor ID cookies expire due to their browser's privacy settings. Some browsers include tracking prevention methods that limit the lifetime of cookies.
* Opens a different browser on the same computer. One unique visitor is counted per browser.
* Opens a private browsing session (such as Chrome's Incognito tab). One unique visitor is counted per browsing session after all tabs are closed.
* Visits your site on different devices. One unique visitor is counted per device.
* Visits your site after more than 13 months of inactivity.

Consider using [Stitching](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) in Customer Journey Analytics to identify the same person using multiple browsers or multiple devices.

## Behavior that does not affect unique visitor count

A new unique visitor is *not* counted, as long as the visitor identifier is preserved:

* Closes their browser (for less than 13 months)
* Upgrades their browser to the latest version
* Restarts their computer
