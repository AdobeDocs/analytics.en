---
title: Options to mitigate the effect of browser cookie limitations
description: Learn how to mitigate the effect of browser cookie limitations to improve data collection for Adobe Analytics.
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
---
# Options to mitigate the effect of browser cookie limitations

This document discusses options for preserving persistent visitor identification across properties and solutions as major browsers implement tracking prevention measures for cookies.

Adobe Analytics relies on first-party cookies to record a visitor's on-site activity. Analytics also relies on third-party cookies to understand a visitor's off-site activity, such as activity on other domains you own. Third-party cookies are blocked on many browsers and will be largely unavailable with Chrome's upcoming removal of support (currently planned for 2022). First-party cookies are allowed on all browsers but have a limited expiry on Safari and other browsers under Apple's [ITP tracking prevention](https://webkit.org/tracking-prevention) measures. For more information about current limitations on browser cookies, see [Adobe Analytics and browser cookies](cookies.md).

These browser limitations reflect a broader move away from anonymous third-party tracking towards explicit sharing of information between users and brands they trust. To support this move, Adobe provides ways for customers to supplement traditional cookies by including durable identifiers collected via their first-party relationships.  

## Customer Journey Analytics and Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) and [Cross-Device Analytics](/help/components/cda/overview.md) allow users to include durable identifiers, such as hashed logins, in addition to cookies. This allows you to understand the customer journey across devices and, in the case of Customer Journey Analytics, across online and offline channels:

* **Customer Journey Analytics** is built on Adobe Experience Platform and provides the flexibility to combine online and offline data in Analysis Workspace, based on any common customer ID. You can specify which ID you want use for any given analysis and explore the data in Analysis Workspace. Analytics Select, Prime, and Ultimate customers are eligible to purchase this as an add-on product.

* **Cross-Device Analytics** is an enhancement to traditional Adobe Analytics that allows customers to use alternate identifiers to visitors. This capability lets you move from a device-centric view to a person-centric view. Cross-Device Analytics is available to Analytics Ultimate customers.

## Server-side data collection

Server-side collection provides the flexibility to provide your own identifier rather than relying on browser mechanisms for setting cookies.

You can submit data to Analytics server-side using either the [Data Insertion API](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) or the [Bulk Data Insertion API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). Bulk Data Insertion API is recommended for new server-side implementations. For a comparison of the two APIs, see “[Which Adobe Analytics tool should I use](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)."

## More information

For practical steps your business can take to transition away from third-party cookies, see [Acquire and keep customers in a cookieless world with Adobe](https://business.adobe.com/solutions/cookieless.html) and the in-depth [Thinking beyond the third-party cookie: Your complete guide to a world without third-party cookies](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf)."

>[!MORELIKETHIS]
>
>[Adobe Analytics and browser cookies](cookies.md)
