---
title: Visitor ID Service migration considerations for Adobe Analytics
description: An overview of how Adobe Analytics interfaces with the Visitor ID Service.
---
# Visitor ID Service migration considerations for Adobe Analytics

If your organization plans to move to the Visitor ID Service with an existing Analytics implementation, there are some important topics to consider. These considerations are important to retain visitor identification integrity, and to understand how the ID Service operates in the presence of an existing Analytics implementation.

## How the Visitor ID Service interfaces with legacy Analytics visitor cookies

Because AppMeasurement has its own method to identify visitors, some visitors might have legacy Analytics cookies when an organization deploys the Visitor ID Service. The following list outlines how a visitor is identified under varying circumstances.

* **No visitor cookies present**: The ID service assigns an Experience Cloud ID (`mid`).
* **An `s_vi` cookie exists**: The ID service writes the existing legacy Analytics ID (`aid`) to the `AMCV` cookie in addition to an Experience Cloud ID (`mid`). Since `aid` is higher in the [Order of operations](overview.md), the legacy Analytics ID is the visitor identifier until the `AMCV` cookie expires or is cleared. When a grace period is enabled, the ID Service includes both the `mid` and `aid` in its response.
* **A fallback cookie exists**: The ID service does not write the fallback cookie (`fid`) to the `AMCV` cookie. Instead, visitors receive an Experience Cloud ID (`mid`) as if they were a new visitor.

## Visitor ID Service grace period

If you have multiple implementations sending data to the same report suite and you can implement the Visitor ID Service on only some implementations, Adobe recommends configuring a grace period. For example, if the support section of your site is managed by a separate tagging solution, you might have the Visitor ID Service deployed on the rest of your site before the support section. Without a grace period, new visitors who view the support section receive a legacy Analytics visitor ID, causing two separate visitors to be counted. With a grace period, the Visitor ID service issues both an Experience Cloud ID (`mid`) and a legacy Analytics visitor ID (`aid`) so that areas of your site without the ID Service remain consistent identifying visitors.

If you coordinate the deployment of the Visitor ID Service across all areas of your site, you do not need a grace period. To configure a grace period, contact [Adobe Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html).

## Cross-domain tracking

Some legacy Analytics visitor ID implementations might use "friendly third-party cookies", where two domains share the same visitor cookie on a common domain like `data.example.com`. Since friendly third-party cookies are still third-party cookies, most modern browsers reject them, causing Analytics to rely on a fallback ID (`fid`) for visitor identification. Moving to the ID Service allows all domains to set the `AMCV` cookie in a first-party context, increasing their viability to retain a visitor ID.

While the Visitor ID Service attempts to set a third-party cookie for cross-domain tracking (the [`demdex` cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), it is often rejected by most modern browsers. Consider using the [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) method to pass the Experience Cloud IDs between domains that you own.

## Server-side tracking

You can call [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) to obtain the Experience Cloud ID (`mid`) and [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) to obtain the legacy Analytics ID (`aid`). Adobe recommends checking for both to preserve visitor identification logic.
