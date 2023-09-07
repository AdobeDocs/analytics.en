---
description: Overview of what data Adobe Analytics collects and other privacy considerations.
keywords: privacy
title: Privacy overview
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
---
# Privacy overview

Adobe wants to enable your organization so that you can comply with applicable privacy laws and regulations. See [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) for more information. With respect to Adobe Analyics, Adobe acts as a "data processor" and you are the "data controller" (or equivalent under applicable privacy and data protection laws). It is up to your organization to disclose how you use Adobe's products and services because your organization exclusively controls how to implement Adobe's solutions. Your organization is responsible for complying with your own privacy policy, your service agreement with Adobe, and all applicable laws.

Adobe strongly recommends adhering to the following overarching concepts:

* **If you collect personal data, make sure that you comply with privacy laws and regulations.** Custom variables allow you to collect virtually anything that you can access; however, you must also consider your organization's privacy policy and applicable laws.
* **Provide easy-to-find and easy-to-understand privacy information for your organization to your customers.** Helpful information includes opt-out links, how their browsing data is used, and how you use or plan to use Adobe's services.
* **Be aware of both local laws and international laws that apply to you.** If your organization operates at a global scale, some international laws can apply.

## Data collection breakdown

Adobe offers multiple data collection libraries to assist in sending data to Adobe. Notable examples include:

* **AppMeasurement**: A library designed to send data directly to Adobe Analytics.
* **Web SDK**: A library designed to send data to the Adobe Experience Platform Edge network, which then forwards that data to Adobe Analytics.
* **Tags**: A web-based UI that allows you to configure your implementation without requiring access to a website or app's source code beyond the initial tag implementation. Extensions are available for both AppMeasurement and the Web SDK.

Adobe Analytics can collect the following types of data:

| Type of data | Details | Example variables containing this data |
| --- | --- | --- |
| Page names or URLs of web pages on your site | Always collected in order for Adobe Analytics to function. URL or page name is required for every hit. | [Page](../components/dimensions/page.md), [Page URL](../components/dimensions/page-url.md) |
| Time-based data | Always collected in order for Adobe Analytics to function. Timestamp is required for data collection, and time-based data is derived from the timestamp. | [Time spent on page](../components/dimensions/time-spent-on-page.md), [Hour of day](../components/dimensions/hour-of-day.md), [AM/PM](../components/dimensions/am-pm.md), [Weekday/Weekend](../components/dimensions/weekday-weekend.md), [Day of week](../components/dimensions/day-of-week.md), [Month of year](../components/dimensions/month-of-year.md) |
| Data from web pages on other sites | Adobe cannot collect data on unaffiliated sites where you cannot alter the website or app's source code. Data collection libraries collect the referring URL by default when a visitor arrives to your website. You can customize your implementation to collect data within query strings after website or app visitors arrive.  | [Referrer](../components/dimensions/referrer.md), [Referring domain](../components/dimensions/referring-domain.md) |
| Anonymized visitor ID's | Data collection libraries generate and reference a visitor ID for each browser visiting your site. This ID is stored in a cookie. If a data collection library cannot set cookies for any reason, the library uses a fallback method of visitor identification using IP address and user agent string. See [Adobe Analytics and browser cookies](cookies/cookies.md) for more information. | [Unique visitors](../components/metrics/unique-visitors.md) |
| Identifiable visitor ID's | Adobe does not automatically collect custom visitor ID's. However, you can customize your implementation to collect this data. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| External search terms | External search data includes keywords that originate from search engines. Data collection libraries look for this data based on the referring URL. However, many modern search engines no longer include this information. | [Search keyword](../components/dimensions/search-keyword.md) |
| Internal search terms | Internal search data includes keywords that originate from within your website or app's search capabilities. Adobe does not automatically collect internal search data. However, you can customize your implementation to collect this data. This practice is common for organizations who use Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Computer and browser specifications | AppMeasurement automatically collects low entropy browser hints, such as the browser type, operating system type, and if the device is desktop or mobile. Custom configuration is required to collect high entropy hints, such as the browser's specific version/build, the device model, or the operating system version. See [Client hints overview](client-hints.md) for more information. | [Browser](../components/dimensions/browser.md), [Operating system](../components/dimensions/operating-systems.md), [Mobile dimensions](../components/dimensions/mobile-dimensions.md), [Monitor resolution](../components/dimensions/monitor-resolution.md) |
| Geolocation information | Adobe offers the ability to enable or disable the collection of geolocation data for each website or app (at a report suite level). Geolocation data collection is enabled by default. Data collection libraries include geolocation if it is enabled. | [Cities](../components/dimensions/cities.md), [Regions](../components/dimensions/regions.md), [Countries](../components/dimensions/countries.md) |
| IP address | Adobe offers the ability to obfuscate the last octet or completely obfuscate the visitor's IP address when storing this data. EMEA customers typically have IP address completely obfuscated by default. Regardless of obfuscation setting, IP address is not available as dimension in Adobe Analytics; it is only included in [Data feeds](../export/analytics-data-feed/data-feed-overview.md). | None |
| Form information provided on your site | All implementation types require configuration to collect this data. You can include this data in custom variables. | [eVar](../components/dimensions/evar.md) |
| Ads or links clicked when on your site | Collected by default if using a data collection library. Additional information, such as the location of clicks, is available when you enable Activity Map. | [Activity Map](../analyze/activity-map/activity-map.md), [Exit link](../components/dimensions/exit-link.md), [Download link](../components/dimensions/download-link.md) |
| Products purchased on your site | All implementation types require configuration to collect this data. Adobe offers several default variables to collect this information. | [Product](../components/dimensions/product.md), [Orders](../components/metrics/orders.md), [Revenue](../components/metrics/revenue.md) |

{style="table-layout:auto"}

See the navigation menu under [Dimensions overview](../components/dimensions/overview.md) and [Metrics overview](../components/metrics/overview.md) for more variables that Adobe can potentially collect data under.

## Data processing locations

Adobe maintains three data processing locations for Adobe Analytics. These sites receive raw data and process it into a report suite, which is optimized for data storage and reporting retrieval. These data processing locations reside in **Oregon**, **London**, and **Singapore**. See [Adobe Analytics security overview](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf) for more information.
