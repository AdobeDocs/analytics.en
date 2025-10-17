---
title: Visitor identification in Adobe Analytics
description: Learn how to identify visitors in Adobe Analytics using the latest best practices.
---
# Visitor identification in Adobe Analytics

<!-- Intro, always recommend using the visitor ID service -->

>[!NOTE]
>
>Each Analytics visitor ID is tied to a profile on Adobe's servers. These visitor profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.

## Adobe Analytics identification order of operations

When Adobe receives a hit, the following checks are made in order. If a given property is present, Adobe uses that identifier for the hit. If multiple identifiers are present in a hit, only the first method is used.

Order used | Query parameter | Present when
--- | --- | ---
**1<sup>st</sup>** | `vid` | The [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable is set.
**2<sup>nd</sup>** | `aid` | Visitor has an existing [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Set on implementations without or prior to implementing the Visitor ID service.
**3<sup>rd</sup>** | `mid` | Visitor has an existing [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie. Set on implementations using the [Adobe Experience Cloud Identity service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Adobe recommends using the ID service for all implementations where possible.
**4<sup>th</sup>** | `fid` | Visitor has an existing [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie, or if `aid` and `mid` could not be set for any reason.
**5<sup>th</sup>** | IP Address, User Agent, Gateway IP Address | Last resort to identify a unique visitor if the visitor's browser does not accept cookies.

## Behavior that affects unique visitor count

Unique visitor identifiers are typically stored in a browser cookie. A new unique visitor is counted if they perform any of the following:

* Clears their cache at any time. One unique visitor is counted for a hit after each time their cache is cleared.
* Opens a different browser on the same computer. One unique visitor is counted per browser.
* Opens a private browsing session (such as Chrome's Incognito tab). One unique visitor is counted per browsing session after all tabs are closed.
* Browses your site on different devices. One unique visitor is counted per device.
 
Consider using [Stitching](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) in Customer Journey Analytics to identify the same person using multiple browsers or multiple devices.

## Behavior that does not affect unique visitor count

A new unique visitor is *not* counted, as long as the visitor identifier is preserved:

* Closes their browser for an extended period
* Upgrades their browser to the latest version
* Restarts their computer
