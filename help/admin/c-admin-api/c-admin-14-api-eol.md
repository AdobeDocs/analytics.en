---
description: Link to Adobe Analytics Admin API on github.
title: Adobe Analytics 1.4 API EOL FAQ
feature: Admin Tools
role: Admin
---
# Adobe Analytics 1.4 API EOL FAQ

## End-of-Life (EOL) notice

**What is being retired?**

* Adobe Analytics 1.4 APIs

* Adobe Analytics WSSE Authentication

**When is it being shut down?**

These services are being retired on August 12, 2026. They will no longer be accessible after this date.

## 1.4 APIs

**What are these services?** 

The [Adobe Analytics 1.4 APIs](https://developer.adobe.com/analytics-apis/docs/1.4/) are a collection of APIs providing for a wide range of actions, such as reporting, classifications, data feeds, and report suite configurations.

**What do I need to do to migrate?**

The [Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/) offer a migration path forward for 1.4 API users. Customers currently using the 1.4 APIs can migrate their integrations to the 2.0 APIs (the same APIs that the Adobe Analytics application depends on) and take advantage of the latest features.

The 2.0 APIs allow you to perform almost any action that you can perform in the Analytics user interface, such such as reporting or managing components like segments and calculated metrics. 

**Do the 2.0 APIs offer the same features as the 1.4 APIs?**
Any capabilities that are available in the 1.4 APIs can be accomplished using the [Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/). Some functionality  provide the same capabilities as are available in the 1.4 APIs, have the same allow you to perform almost any action that you can perform in the Analytics user interface, such as reporting or managing components like segments and calculated metrics.

## WSSE Authentication

**What are these services?**

WSSE authentication is a legacy authentication protocol supported by the Analytics 1.4 APIs. It has been replaced by the OAuth-based authentication options provided in the [Adobe Developer Console](https://developer.adobe.com/console/home). 

**What do I need to do to migrate?** 

WSSE customers must update their authentications to use credentials provisioned in the Adobe Developer Console. To do this, log in to the [Adobe Developer Console](https://developer.adobe.com/console/home) to create a project for your Analytics 2.0 API integration. Select between the OAuth User and OAuth Server-to-Server authentication methods.

## Questions

Q: **Does this impact my existing Adobe IO projects for the Analytics APIs?**

A: Any existing projects using the Analytics 1.4 APIs will be impacted. Those integrations must be migrated to the [Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/) before the EOL deadline.

Q: **I've shared my Adobe credentials with another product or application that uses the Analytics APIs. Are they impacted?**

A: If that product or application uses your WSSE credential and/or calls the Analytics 1.4 APIs, it is impacted and will need to migrate before the EOL deadline. Please reach out to the product or application provider for more details on their migration plans and timeline.

Q: **I'm not sure what Adobe Analytics API we are using.**

A: You can identify which API you are using by the address being called in your integration. 

The Adobe Analytics 1.4 APIs are accessed by calling any of the URLs below:
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

The [Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/) are accessed by calling the following URL:
* https://analytics.adobe.io

If you are using api*.omniture.com, you need to migrate to the [Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/).

Q: **Are the Adobe Analytics 2.0 APIs identical to the 1.4 APIs? If not, what are the biggest differences?**

A: The Adobe Analytics 2.0 APIs are not identical to the 1.4 APIs, but they do offer comparable features, including the following benefits:

* Faster response times with simpler and more efficient query methods, eliminating the need for polling

* Programmatic capability for queries and dynamic report updates

* More graceful error handling

* Flexible functioning to accomplish anything that you can accomplish from Analysis Workspace

* Consistency and matching of API calls to UI actions

* Access to all Attribution IQ models used in Analysis Workspace

* Access to all Anomaly Detection algorithms used in Analysis Workspace

* The ability to integrate with other Experience Cloud products

* Increased capacity for multiple breakdown reports

* Access to the latest Analytics features 

The [Migrating to Adobe Analytics 2.0 APIs](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) guide discusses the key differences between the 1.4 and 2.0 APIs. Additional information is also available in the [Analytics 2.0 API FAQ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

Q: **Does this impact data collection?**

A: The Adobe Analytics 1.4 EOL does not impact your tagging solutions, such as Tags (formerly Adobe Launch), WebSDK, or AppMeasurement.js. However, if you use the 1.4 Data Sources, Data Insertion, or Classifications APIs to collect or enhance your data, you must migrate those workflows to the Adobe Analytics 2.0 APIs. Please refer to the [2.0 API Endpoints guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/) for more details.

Q: **What do I do if my question wasn't answered in this FAQ?**

A: If you still have questions, please reach out to your Adobe account representative.

