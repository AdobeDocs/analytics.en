---
title: DFA Integration - End-of-life Information
description: Why is Adobe end-of-lifing the DFA Data Connector and what alternatives are there?
exl-id: 01dbedc7-f878-4d9b-999f-a05997a5c0ed
---
# DFA Integration - End-of-life Information

Adobe recently announced [its plans to end-of-life Data Connector](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), a legacy toolset for integrating 3-rd party data (e.g. ESP, VOC, etc.) with Adobe Analytics.

## Why are Data Connectors going into End-of-Life?

The supported platform for partner integration is [Adobe Exchange](https://exchange.adobe.com/experiencecloud), which is designed to facilitate Adobe Digital Experience application integration, third party CXM integration and to support the various data requirements of both clients and partners well into the future. Many partners who had built their integrations using Data Connectors have already migrated those integrations to Adobe Exchange, with more partners planning to do so.
  
## Why is the DFA Integration going into End-of-Life?

In [January 2020, Google announced](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) that it will phase out third-party cookies in Chrome by 2022. This follows industry standards that Apple and Mozilla have set in place for their Safari and Firefox browsers, respectively. The DFA integration relies heavily upon third-party cookies and will therefore become ineffective and obsolete with the removal of third-party cookies across the three major internet browsers. Google [reinforced this stance in March 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) by announcing they will not release an alternative solution.
 
Unfortunately, Google — which owns the DFA integration — is unlikely to replicate it on the Adobe Exchange platform. Therefore, we are moving forward under the assumption that, once Data Connectors goes offline, the existing integration will cease to function and will not have a productized replacement. 
 
An important and additional factor is the "view-throughs" capability of the DFA integration. It allows Adobe Analytics to track cases where a user saw a display ad, did not click, but then later visited the web site. "View-throughs" are based on third-party cookies, which will continue to be phased out over the course of 2021. This is a market-wide issue, not just an Adobe issue. As for now, no alternatives exist for replicating this data.
 
## What alternatives exist for you?

For customers who are interested in integrating display ad data (without “view-throughs”) into Adobe Analytics, we currently have the following options:

* Adobe Advertising Cloud DSP customers can leverage [a productized integration with Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) to set display ad data from Google to Adobe Analytics. This integration is our best alternative and would be our recommendation to customers. The Ad Cloud DSP allows customers to deliver connected experiences across all advertising channels, including paid search, display, video and others. Learn more [here](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). However, the Ad Cloud DSP will also be impacted by the loss of third-party cookies. 
* Adobe Experience Platform and [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), which provide capabilities around display ad integration with other data sources. Customers can download their display data from their paid search provider and upload that data to Experience Platform. Then they bring the data directly into CJA to analyze alongside their other data sets.
* Adobe Consulting (Engineering Architects) can build a custom solution to ingest display ad metrics into Adobe Analytics. This solution is still in development and any customers interested in joining the beta are welcome to participate. More details regarding features, availability, and cost will be provided as they become available.
* You can manage your own display ad integration, using Data Sources functionality as well as Classifications in Adobe Analytics. Import your paid search and display data manually using Data Sources and Classifications [as described here](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Note: this document refers to paid search, but the use case and concept is the same and can be applied to display).

For additional questions or support, please reach out to [Adobe Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html).
