---
title: Global report suites in Adobe Analytics
description: Understand the advantages and requirements to using a global report suite.
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
---
# Global report suite considerations

A global report suite is a report suite that collects data from all domains and apps that your organization owns. This data collection technique requires preparation and can require coordination between teams within your organization.

## Advantages

Adobe recommends implementing a global report suite in most cases.

* **Aggregated data:** Global report suites enable you to see KPI's and success events across your owned sites. Segmentation and virtual report suites can be used to view site-specific data.
* **Support for Cross-Device Analytics:** CDA requires a report suite that collects data from multiple places, such as your website and mobile app. Separate devices can stitch data together if implemented correctly. See [Cross-Device Analytics](../../components/cda/overview.md) in the Components user guide for more information.
* **No need for more than one report suite:** All data can be collected in a single report suite, so it is less likely for a developer to mistakenly send data to the wrong report suite.
* **No need for rollups:** Rollups are a fairly dated feature that aggregates individual report suite data on a daily basis. Rollups do not deduplicate visit or visitor data, which can lead to inflated numbers. See [Rollups](../../admin/c-manage-report-suites/rollup-report-suite.md) in the Admin user guide for more information.
* **Save time:** Workspace projects, classifications, segments, and calculated metrics are tied to the same global report suite. Administrators spend less time managing these components and data governance.
* **More accurate cross-brand attribution:** If a visit starts on one site then clicks to another of your owned sites before triggering a success event, attribution is accurately collected. For exampple, a visitor clicks a paid search link, and lands on site A. They then click a link to site B, then make a purchase. A global report suite correctly attributes that purchase back to paid search. 
* **Simplified implementation:** Since all brands/sites send data into the same report suite, your implementations across each site are aligned. This enforced governance ensures a specific dimension or metric is saved in the same eVar or event. Administrators, testers, tag management owners, and analysts benefit from this simplification.

>[!NOTE]
>
>Coordinating a global report suite implementation is a large project. Adobe recommends working with a consultant to reduce complications and issues that arise.

## Starting a new implementation with a global report suite

Use the following general guidelines to understand the process of implementing a global report suite.

1. Create the global report suite in Adobe Analytics. See [Create a report suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) in the Admin user guide for more information.
1. Work with teams in your organization responsible for each domain. Many teams have reporting requirements specific to their area of the business.
1. Record and aggregate all of these requirements in a [Solution design document](solution-design.md). If teams have similar requirements for a dimension, they can use the same custom variable. For example, if site A and site B both require a breadcrumb dimension, implementations for both sites can send that data through eVar1.

   >[!IMPORTANT]
   >
   >Make sure that any given custom variable is used similarly across domains. Do not use the same eVar or event for different purposes across your sites.
1. Make sure that each domain has a data layer to simplify data collection. Data can still be collected without a data layer, but the reliability and longevity of your implementation decreases, especially as your site goes through redesigns.
1. Use Adobe Experience Platform Launch to implement Analytics. Different sites will likely require different data elements. Use rules specific to each domain to make sure each data element is correctly populated, then assign those data elements to their respective eVars and events. See [Launch overview](https://experienceleague.adobe.com/docs/ launch/using/overview.html) in the Adobe Experience Platform Launch user guide.
1. Include the [Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/ id-service/using/home.html) and use the [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/ id-service/using/id-service-api/methods/appendvisitorid.html) function. This function merges visitor data when users click from one domain to another.

## Modifying an existing implementation with a global report suite

The process of moving an existing implementation across multiple sites to a single global report suite requires more time and coordination between teams in your organization.

1. Determine if you want to use one of your existing report suites, or start fresh with a new report suite. If you want to change the uses for existing variables in your implementation, starting with a new report suite is recommended.
2. Determine a cutover date for when you want to make the switch to a global report suite. The best time to make a cutover is between two significant reporting periods, or alongside major changes to your site. Examples include the start of a fiscal quarter or year, during a site refresh, or change to a new tag management system.
3. Follow the steps above (create a report suite, gather reporting requirements in a solution design document, and establish a data layer on each site). When implementing Launch, validate your implementation using a development version of your website.
4. Once you have confirmed your implementation is working on dev, push your Launch implementation live on the cutover date.

## Related pages

[Moving from multi-suite tagging to a global report suite and virtual report suites](../../components/vrs/vrs-considerations.md)
[Comparing rollups and global report suites](../../admin/c-manage-report-suites/rollup-report-suite.md)
