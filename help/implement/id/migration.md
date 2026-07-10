---
title: Visitor ID Service migration considerations for Adobe Analytics
description: An overview of how Adobe Analytics interfaces with the Visitor ID Service.
exl-id: da1f9917-5254-41fb-9e2c-c94f66a22360
TQID: https://experienceleague.adobe.com/NnZ-Vv2M5cWkfekbVX1B-dFesdtxy50fMdTlwPYviYQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Visitor ID Service migration considerations for Adobe Analytics

If your organization plans to move to the Visitor ID Service with an existing Analytics implementation, there are some important topics to consider. These considerations allow you to retain visitor identification integrity and understand how the Visitor ID Service operates in the presence of an existing Analytics implementation.

>[!TIP]
>
>This page only applies to existing AppMeasurement or Analytics extension implementations, and are adding the Visitor ID Service or upgrading to a Web SDK implementation. In other words, your implementation uses a legacy Analytics ID (`aid`) and are moving towards using an ECID (`mid`). All Web SDK implementations use the [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home), which uses an ECID (`mid`) by default.

## How the Visitor ID Service interfaces with legacy Analytics visitor cookies

Because AppMeasurement has its own legacy method to identify visitors, some visitors might have existing Analytics cookies when an organization deploys the Visitor ID Service. The following list outlines how a visitor is identified under varying circumstances.

* **No visitor cookies present**: The Visitor ID Service assigns an ECID (`mid`).
* **An `s_vi` cookie exists**: The Visitor ID Service writes the existing legacy Analytics ID (`aid`) to the `AMCV` cookie in addition to an ECID (`mid`). Since `aid` is higher in the [Order of operations](overview.md), the legacy Analytics ID is the visitor identifier until the `AMCV` cookie expires or is cleared. When a grace period is enabled, the Visitor ID Service includes both the `mid` and `aid` in its response.
* **A fallback cookie exists**: The Visitor ID Service does not write the fallback cookie (`fid`) to the `AMCV` cookie. Instead, visitors receive an ECID (`mid`) as if they were a new visitor.

## Visitor ID Service grace period

If you have multiple implementations sending data to the same report suite and you can implement the Visitor ID Service on only some implementations, Adobe recommends configuring a grace period. For example, if the support section of your site is managed by a separate tagging solution, you might have the Visitor ID Service deployed on the rest of your site before the support section. Without a grace period, new visitors who view the support section receive a legacy Analytics visitor ID, causing two separate visitors to be counted. With a grace period, the Visitor ID Service issues both an ECID (`mid`) and a legacy Analytics visitor ID (`aid`) so that areas of your site without the Visitor ID Service remain consistent identifying visitors.

If you coordinate the deployment of the Visitor ID Service across all areas of your site, you do not need a grace period. To configure a grace period, contact [Adobe Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html). Grace periods can be configured for up to 180 days, and can be renewed. Adobe recommends discontinuing the grace period once your entire property is configured to use the Visitor ID Service.

## Cross-domain tracking

Some legacy Analytics visitor ID implementations might use "friendly third-party cookies", where two domains share the same visitor cookie on a common domain like `data.example.com`. Since friendly third-party cookies are still third-party cookies, many modern browsers reject them, causing Analytics to rely on a fallback ID (`fid`) for visitor identification. Moving to the Visitor ID Service allows all domains to set the `AMCV` cookie in a first-party context, increasing their viability to retain a visitor ID.

While the Visitor ID Service attempts to set a third-party cookie for cross-domain tracking (the [`demdex` cookie](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), it is often rejected by modern browsers. Consider using the [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) method to pass a visitor's ECID (`mid`) between domains that you own.

## Server-side tracking

You can call [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) to obtain the ECID (`mid`) and [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) to obtain the legacy Analytics ID (`aid`). Adobe recommends checking for both to preserve visitor identification logic.
