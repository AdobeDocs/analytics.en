---
description: Overview of what data Adobe Analytics collects and other privacy considerations.
keywords: privacy
title: Privacy overview
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
---
# Privacy overview

Visitors can learn more about how Adobe generally uses information it collects in the [Adobe Privacy Center](https://www.adobe.com/privacy.html). It is up to your organization to disclose how you use Adobe's products and services because your organization exclusively controls how to implement Adobe's services. Your organization is responsible for complying with your own privacy policy, your service agreement with Adobe, and all applicable laws.

Adobe strongly recommends adhering to the following overarching concepts:

* **Avoid collecting personally identifiable information in Adobe Analytics.** Custom variables allow you to collect virtually anything that you can access; however, you must also consider your organization's privacy policy and applicable laws.
* **Provide visitors with easy-to-find and easy-to-understand information regarding opt-out information.** Allow them to opt out of anything that is not strictly necessary. Most countries in the European Union do not consider analytics cookies strictly necessary.

## Data collection breakdown

Adobe Analytics either automatically collects or can potentially collect the following types of data:

| Type of data | Explanation | Example variables containing this data |
| --- | --- | --- |
| Page names or URLs of web pages on your site | Always collected. URL or page name is required for every hit. | [Page](../components/dimensions/page.md), [Page URL](../components/dimensions/page-url.md) |
| Time-based data | Always collected. Timestamp is required for data collection, and time-based data is derived from the timestamp. | [Time spent on page](../components/dimensions/time-spent-on-page.md), [Hour of day](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Weekday/Weekend](../components/dimensions/weekday-weekend.md), [Day of week](../components/dimensions/day-of-week.md), [Month of year](../components/dimensions/month-of-year.md) |
| Data from web pages on other sites | Adobe cannot collect data on unaffiliated sites where you cannot alter the website's source code. AppMeasurement automatically collects the referring URL when a visitor arrives to your website. You can customize your implementation to collect data within query strings after they arrive on your site.  | [Referrer](../components/dimensions/referrer.md), [Referring domain](../components/dimensions/referring-domain.md) |
| Anonymized visitor ID's | AppMeasurement automatically generates and references a visitor ID for each browser visiting your site. This ID is stored in a cookie. If cookies are not available for a given implementation, Adobe Analytics uses a fallback method of visitor identification using IP address and user agent string. See [Adobe Analytics and browser cookies](cookies/cookies.md) for more information. | [Unique Visitors](../components/metrics/unique-visitors.md) |
| Identifiable visitor ID's | Adobe does not automatically collect custom visitor ID's. However, you can customize your implementation to collect this data. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| External search terms | AppMeasurement attempts to automatically collect this data based on the referring URL. However, many modern search engines no longer include this information. | [Search keyword](../components/dimensions/search-keyword.md) |
| Internal search terms | Adobe does not automatically collect internal search data. However, you can customize your implementation to collect this data, and is a common practice for organizations who use Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Computer and browser specifications | AppMeasurement automatically collects low entropy browser hints, such as the browser type, operating system type, and if the device is desktop or mobile. Configuration is required to collect high entropy hints, such as the browser's specific version/build, the device model, or the operating system version. See [Client hints overview](client-hints.md) for more information. | [Browser](../components/dimensions/browser.md), [Operating system](../components/dimensions/operating-systems.md), [Mobile dimensions](../components/dimensions/mobile-dimensions.md), [Monitor resolution](../components/dimensions/monitor-resolution.md) |
| Geolocation information | Adobe offers the ability to enable or disable the collection of geolocation data for each website or app (at a report suite level). Many implementation types, including AppMeasurement, automatically collect this data. | [Cities](../components/dimensions/cities.md), [Regions](../components/dimensions/regions.md), [Countries](../components/dimensions/countries.md) |
| IP address | Adobe offers the ability to obscure the last octet or completely obscure the visitor's IP address when storing this data. EMEA customers typically have IP address completely obscured by default. IP address is not available as dimension in Adobe Analytics; it is only included in raw data ([Data feeds](../export/analytics-data-feed/data-feed-overview.md)). | None |
| Form information provided on your site | All implementation types require configuration to collect this data. You can include this data in custom variables. | [eVar](../components/dimensions/evar.md) |
| Ads or links clicked when on your site | Automatically collected if using AppMeasurement. Additional information, such as the location of clicks, is available with Activity Map enabled. | [Activity Map](../analyze/activity-map/activity-map.md), [Exit link](../components/dimensions/exit-link.md), [Download link](../components/dimensions/download-link.md) |
| Products purchased on your site | All implementation types require configuration to collect this data. Adobe offers several default variables to store this information. | [Product](../components/dimensions/product.md), [Orders](../components/metrics/orders.md), [Revenue](../components/metrics/revenue.md) |

See the navigation menu under [Dimensions overview](../components/dimensions/overview.md) and [Metrics overview](../components/metrics/overview.md) for more variables that Adobe can potentially collect data under.
