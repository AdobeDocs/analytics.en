---
title: Options to mitigate the effect of browser cookie limitations
description: Learn how to mitigate the effect of browser cookie limitations to improve data collection for Adobe Analytics.
---

# Options to mitigate the effect of browser cookie limitations

This document explains how to preserve persistent visitor identification across properties and solutions as major browsers implement tracking prevention measures for cookies.

Adobe Analytics relies on first-party cookies to record a visitor's on-site activity. Analytics also relies on third-party cookies to understand a visitor's off-site activity, such as activity on other domains you own. Third-party cookies are blocked on many browsers and will be largely unavailable with Chrome's upcoming removal of support (currently planned for 2022). First-party cookies are allowed on all browsers but have a limited expiry on Safari and other browsers under Apple's [ITP tracking prevention](https://webkit.org/tracking-prevention) measures. For more information about current limitations on browser cookies, see "[Adobe Analytics and browser cookies](cookies.md).

These browser limitations reflect a broader move away from anonymous third-party tracking towards explicit sharing of information between users and brands they trust. To support this move, Adobe provides ways for customers to supplement traditional cookies by including durable identifiers collected via their first-party relationships.  

## Customer Journey Analytics and Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) and [Cross-Device Analytics](/help/components/cda/overview.md) allow users to include durable identifiers, such as hashed logins, in addition to cookies:

* **Customer Journey Analytics** enables cross-channel analysis in Analysis Workspace through an integration with Adobe Experience Platform. It consolidates online and offline customer data available to you in Experience Platform at query time, using any ID.

* **Cross-Device Analytics** identifies how digital devices map to people and stitches the user journey across any ID using the Adobe Experience Platform Identity Service. It uses either the Adobe Experience Cloud Device Co-op graph, a private device graph, or field-based stitching.

## Server-side data collection

Server-side collection provides the flexibility to provide your own identifier rather than relying on browser mechanisms for setting cookies.

You can import server-side data to Analytics using either the [Data Insertion API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) or the [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). For a comparison of the two APIs, see “[Which Adobe Analytics tool should I use](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)."

## More information

For practical steps your business can take to transition away from third-party cookies, see "[Acquire and keep customers in a cookieless world with Adobe](https://business.adobe.com/solutions/cookieless.html)" and the in-depth "[Thinking beyond the third-party cookie: Your complete guide to a world without third-party cookies](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)."

>[!MORELIKETHIS]
>
>[Adobe Analytics and browser cookies](cookies.md)
