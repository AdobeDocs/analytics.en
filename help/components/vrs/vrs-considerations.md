---
description: Virtual report suites can be used to replace multi-suite tagging. For example, instead of sending data to two separate report suites, you could send data to one and use virtual report suites to limit how much data users have access to. However, access to data is only one of the reasons that separate report suites can be beneficial. Carefully consider the following use cases before making implementation changes with regard to virtual report suites.
keywords: Virtual Report Suite
seo-description: Virtual report suites can be used to replace multi-suite tagging. For example, instead of sending data to two separate report suites, you could send data to one and use virtual report suites to limit how much data users have access to. However, access to data is only one of the reasons that separate report suites can be beneficial. Carefully consider the following use cases before making implementation changes with regard to virtual report suites.
seo-title: VRSs and global/multi-suite tagging considerations
solution: Analytics
title: VRSs and global/multi-suite tagging considerations
topic: Reports and analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
---

# VRSs and global/multi-suite tagging considerations

Virtual report suites (VRS) let you view data from a report suite that is collecting data from your digital properties, but with a segment permanently applied.

Because they function as report suites and can be assigned to user groups just like report suites, VRS can, in some cases, be used to replace multi-suite tagging and thus remove [secondary server calls](/help/admin/c-server-call-usage/overage-overview.md). (Multi-suite tagging is defined as the ability to send data to multiple report suites using a single image request.) For example, instead of sending data for two of your brands into two separate “child” report suites plus a “global” report suite where data across brands is brought together, you can send data from both brands only to the global report suite. You would then use VRS to limit your users’ access to data (by brand) by replicating the child report suites.

 Replacing multi-suite tagging with a global report suite and VRS allows you to simplify your Adobe Analytics implementation and reduce server call consumption, and is generally encouraged as a best practice. However, there are some important limitations of VRS that you should consider when deciding whether to use multi-suite tagging or a single global report suite plus VRS. The following guidelines can help you decide whether implementing virtual report suites built on a global report suite is the right approach for you.

## Guidelines

>[!NOTE]
>
> The following considerations apply ONLY to these cases:
>
>* You are considering changing your implementation to remove child report suites and to rely solely on virtual >report suites to control views into data for end users, or
>* Users of Adobe Analytics at your company will rely on virtual report suites as their primary view of data. 

If you are unsure whether the use cases described apply to you and your organization, consult your other Adobe Analytics administrators, or your Adobe account team. They can help assess your business needs and make a recommendation.

Using virtual report suites to replace multi-suite tagging is recommended if: 

## Publishing segments from Adobe Analytics to the rest of Adobe Experience Cloud is required only at the global-report-suite level, and all users who publish segments have access to the global report suite.

Summary:

* Sharing segments to Adobe Experience Cloud is not supported for virtual report suites.
* Users who need to be able to share a segment to Experience Cloud must have access to a true report suite (parent or child).

Currently, segments cannot be published to Adobe Experience Cloud from a virtual report suite for personalization and targeting. All users who publish segments need access to a true report suite for this purpose. A multi-suite tagging approach creates child report suites at a brand, property, region, etc. level that allow users who do not have access to the global report suite to publish segments against only the set of data made available to them in the child report suite.

For example, your users may have access to virtual report suites for their geographical regions only, but you want them to be able to create and share segments from Adobe Analytics to Adobe Experience Cloud for targeting in Adobe Target. In this case, these users would not be able to publish segments, and you should consider using multi-suite tagging to ensure that users can publish segments.

## You don't need real-time (or "Current Data") reporting at the virtual-report-suite level.

Summary:

* Real-time reports are not supported in virtual report suites, because the data is segmented.
* "Current Data" is not supported in virtual report suites, because it does not support segmentation.

[Real-time reports](/help/admin/admin/realtime/t-realtime-admin.md) and ["Current Data"](/help/admin/data-collection/data-latency.md) are not available in virtual report suites. These features of Reports & Analytics provide access to limited types of data in an accelerated manner, within seconds or minutes. One of the limitations of these views is that they do not support segmentation; in other words, real-time data in Reports & Analytics cannot be segmented. Because a virtual report suite is built using segmentation, it is incompatible with real-time reporting. This affects users who are responding to trends seen in Adobe Analytics within seconds or a few minutes of data collection, such as editors in a newsroom who are adjusting headline stacks based on real-time content consumption. In this case, you should:

* Consider using multi-suite tagging to ensure that each user sees only the real-time data that they should be allowed to see, or
* Grant these users access to a true report suite (global) if they should be allowed access to your complete data set.

## You do not exceed unique value limits for key dimensions in your global report suite(s), or you do not care if your users see "Low Traffic" in their virtual report suites.

Summary:

* Virtual report suites do not have their own unique value limits for dimensions, and inherit them from their parent report suite.
* If your Adobe Analytics users need access to every value of a dimension that frequently receives more than 500,000 unique values per month, consider continuing to multi-suite tag.

In cases of high cardinality (large numbers of unique values in a given dimension, like Product SKUs or Pages), Adobe Analytics buckets rarely encountered values each month into an aggregated “Low Traffic” line item within any given dimension in a report suite. Values that are included in the “Low Traffic” bucket cannot be segmented. This allows Adobe Analytics queries to return quickly, while focusing on the top 500,000 line items that are seen most often for the dimension on your digital properties. (For example, this might be your top 500,000 page names.) You can read more about unique value limits [here](/help/admin/data-collection/metrics-uniques-high-numbers.md).

Virtual report suites do not have their own set of 500,000 unique values per dimension per month. If the report suite on which a VRS is based has exceeded 500,000 unique values for a given dimension, and has started to combine lower-frequency values into the “Low Traffic” line item for that dimension, you may see “Low Traffic” in the virtual report suite as well.

**Example**: a media conglomerate owns 100 web properties. Each property publishes a few thousand news articles monthly, in addition to hosting all articles from previous months, and all properties combine into a global report suite. In the 'Article Name' dimension in the global report suite, assume that there are 4 million unique article names each month, from the various properties. The top 500,000 values that comprise the bulk of the traffic are shown and can be segmented, but the remaining 3.5 million values are bucketed in the “Low Traffic” line item.

In this case, you could create 100 virtual report suites for the teams who work on the individual properties. While this is acceptable, consider that in the 'Article Name' dimension in each virtual report suite, the values that are shown as distinct line items are only those from the top 500,000 in the global report suite for the given property. Virtual report suites do not get their own allocation of 500,000 unique values per dimension. Values that rolled up into the “Low Traffic” item in the global report suite will not be shown individually in the VRS. This can cause confusion among users who expect to see an entire set of dimension values in a virtual report suite and instead end up seeing only the high-traffic values.

If you know that you regularly exceed unique value limits in your global report suite or in your existing child report suites, consider whether users need access to those infrequently seen values before migrating to virtual report suites. If your users need access to every unique value in a dimension that current exceeds unique value limits in your global report suite, consider continuing to use multi-suite tagging to provide this access.

Also note that Adobe Customer Care can increase unique value limits for a global report suite on a limited basis for a small number of dimensions, which may eliminate this problem entirely. Consult your account team and Customer Care for more information. 

## You can use your available set of custom dimensions (eVars and props) and metrics (events) in your global report suite to track all critical data points across all properties.

Summary:

* Virtual report suites do not have their own sets of dimensions and metrics; they inherit these from their parent report suite.
* Therefore, the parent report suite must be able to capture all relevant dimensions and metrics for each property that is combined within it using only the custom dimensions and metrics available to the global report suite (325 and 1000, respectively).

One current advantage of multi-suite tagging is that you can allow different properties, brands, regions, etc. to capture different types of data. For example, one business unit might use eVar76 to capture 'Internal Search Keywords', while another business unit might use that same eVar to capture 'Video Name'. Groups have freedom to implement Adobe Analytics according to their unique needs.

With a global report suite, all properties must pass the same data points into the same dimension and metrics. In the previous example, these two brands would need to align on eVar76 being used for either 'Internal Search Keywords' or 'Video Name', and then put the other data point into a different dimension in their respective implementations. Failure to do this will lead to corruption of dimensions and/or metrics in the global report suite. This tends to be a problem in situations where various properties, brands, regions, etc. that you support (with individual report suites) use their full contingent of available custom dimensions or metrics. Consequently, they would not be able to accommodate reserving some of their dimensions or metrics for the tracking needs of other properties, brands, regions, etc.

The maximum number of Adobe Analytics custom dimensions per report suite is 325, and the maximum number of custom events per report suites is 1000. Moving to a global report suite therefore requires that all critical data points across all digital properties can be tracked using the same 325 custom dimensions and 1000 custom events.

If you find yourself in this situation and are considering moving to a global report suite with VRS, review the various Adobe Analytics implementations at your company to assess the amount of overlap/dissonance in these implementations, and to see which dimensions or metrics are not critical to business success. Also consider using [classifications](/help/components/c-classifications2/c-classifications.md) in your global suite to report on values that may currently be using their own dimension. Classifications are automatically available to any VRS based on that global suite. For example, instead of capturing 'Product Name' in eVar5, create a 'Product Name' classification based on the 'Product' dimension.

If consolidating these custom dimensions and events is not feasible, Adobe recommends that you continue to use multi-suite tagging. 

>[!IMPORTANT]
>
>With the introduction of [virtual report suite curation](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), you can now change the name of a given dimension or >metric on a per-VRS basis. If you segment your virtual report suite cleanly, this means that you can now use the >same eVar, prop, or event to capture different things in different virtual report suites. However, passing two >different types of data into the same dimension or metric will make that data point practically unusable in the >global report suite. It could also lead to problems with attribution, as in this example: if a user receives two >values for eVar10, one that is an 'Internal Campaign' on property A and the other which is a 'Page Name' on >property B, this means that success is now split across 'Internal Campaign' and 'Page Name', which should >operate on different levels. Therefore, Adobe does not generally recommend using VRS curation as a workaround >for this particular problem.

## The segments you use with virtual report suites do not divide the data in ways that may confuse your users.

Summary:

* Segmenting data from a global report suite into virtual report suites can create nuanced results that may confuse some users.
* Consider how your segments in virtual report suites can impact dimensions and capabilities such as entry page, referring domain, pathing, etc.

Remember that a virtual report suite is just a segment applied to a report suite; all nuances in segmented data apply to virtual report suites. Segments (and therefore virtual report suites) may be used to slice data in ways that seem non-intuitive to your Adobe Analytics users.

For example, assume that you have two brands, A and B, whose digital properties are sending data into a global report suite. Some users will cross over from the A web site to B web site and vice versa, and this movement from one to the other is visible in pathing in the global report suite. However, if you build virtual report suites for brands A and B, users who access the virtual report suite B may see non-intuitive results for certain dimensions and metrics. A visit that started on brand A and ended on brand B will show no entry page in the virtual report suite B, since the entry page for the cross-site visit began on brand A, which is segmented out of this virtual report suite.

A similar example deals with 'Visit Number'. In the virtual report suite for brand B, users may see some visitors who appear to have a second, third, and fourth visit, but no first visit. This would occur when the customer’s first visit is to brand A, and all subsequent visits are to brand B. Since brand A's data is not included in the virtual report suite, all information about the first visit—including the fact that it happened at all—is not included in this virtual report suite.

Adobe recommends using multi-suite tagging in these scenarios or in other situations where part of a customer’s journey may occur outside of a virtual report suite in a way that may confuse your users. Multi-suite tagging lets you track a journey at a cross-property level in a global report suite but also provides individual teams with their own complete view of the journey at an individual property level. 

## You and your users do not need to be able to view transactions in various national currencies.

Summary:

* Virtual report suites cannot currently report on a different currency than the report suite on which they are based.
* Adobe Analytics does allow you to convert currency when running reports but the exchange rate is based on the current day, even for historical data.

Virtual report suites cannot currently report on a different currency than the report suite on which they are based. If your company and your Adobe Analytics users do their analysis in a single currency, this will not cause a problem for you. However, if you have a significant business need for different regional teams who need to be able to view revenue and similar metrics in their own local currency (which is converted based on the exchange rate at the time of data collection) you should use multi-suite tagging.

This lets you send data into Adobe Analytics in different currencies at the same time. With multi-suite tagging, a transaction which occurs in the Japanese version of your app could be recorded in the global suite in USD. It can be converted from JPY at the given day’s exchange rate, but continue to show in your Japan report suite in JPY. 

>[!NOTE]
>
>While virtual report suites do not allow you to convert revenue data into another currency at a historical rate, >you can still convert currency in a virtual report suite on an ad-hoc basis. You can apply the current day’s >exchange rate to historical data by going to Components > Report Settings. 

## You can use a single Data Feed to receive all of your data from a global report suite.

 Summary:

* Data Feeds can only be created based on true report suites, not virtual report suites.
* However, you can receive a Data Feed from a global report suite and then break it up by brand, property, region, etc.

Data Feeds let you receive a daily or hourly export of all of your Adobe Analytics data at an "event" or “hit” level. Because Data Feeds cannot be pre-segmented before they are delivered to you, using a global report suite with virtual report suites means that you can only receive a Data Feed for your global report suite. You cannot set up Data Feeds for virtual report suites.

However, you can set up as many Data Feeds based on true report suites as you want. After receiving these Data Feeds, you can segment and split them up into any useful configuration. For example, after receiving a Data Feed for a global report suite, you could load the portion of that Data Feed that pertains to your web site into one data warehouse. You could simultaneously load the portion that pertains to your mobile app into a different data warehouse.

Note, however, that some pre-calculated fields in the Data Feed may need to be recalculated after receipt. See item 5 (above) for examples of fields that may need to be recalculated when filtering a Data Feed based on some criteria.

If your organization has a strong need for individual Data Feeds at a brand, property, region, etc. level, you may wish to consider using multi-suite tagging. 

## You do not use an Exchange (data connectors) integration that allows only one partner account per report suite, and you do not have multiple partner accounts that you want to integrate.

Summary:

* Certain Adobe partner integrations into Adobe Analytics are limited to one partner account per report suite.
* Some organizations may wish to use multiple partner accounts in Adobe Analytics, which requires multi-suite tagging.

Adobe Exchange lets you integrate other marketing and ad technology solutions with Adobe Analytics. Examples of available integrations include display advertising, email, VOC, and call center. Due to variances in how data is collected, presented, and integrated, some of Adobe’s partners that you may opt to use with Adobe Exchange have a limitation of one instance of their integration per report suite. Each instance is mapped to an account with the partner.

An example of this is Google DCM. Many companies have multiple DCM accounts, which allows different brands, business units, regions, etc. to manage their displays ads separately from one another. However, when integrating DCM with Adobe Analytics, you can only use one DCM account per report suite. You cannot integrate each of your various DCM accounts into the same report suite. You also cannot set up an integration directly into a virtual report suite.

As a result, multi-suite tagging is the preferred approach if different teams in your organization need to have their own individual account’s data in Adobe Analyics for an Adobe Exchange partner. If you are (or will be) using any Adobe Exchange integrations where different groups manage different accounts, check with the Adobe partner to understand whether multiple accounts per report suite are allowed. 

>[!NOTE]
>
>The term “account” may mean different things to different vendors. In the context of marketing technology, it >usually does not refer to an individual user account, but rather to a set of services made available to an >entire team or organization. So while you may have multiple user names logging in to an Adobe partner’s service, >all of these user names may belong to the same account.

>[!NOTE]
>
>Any “pre-click” (summarized/aggregated) metrics that are imported from an Adobe Exchange partner are not >available for segmentation, and therefore may not be visible in a virtual report suite. Examples of such metrics >include emails sent or display ad impressions, both of which occur off-site/off-app and are imported into Adobe >Analytics in an aggregated form.

## You do not rely heavily on Summary Data Sources at a property, brand, region, etc. level.

Summary:

* 'Summary Data Sources' let you import aggregated metrics into Adobe Analytics at a report-suite level.
* Moving to a global report suite with virtual report suites would require that all 'Summary Data Sources' uploads occur in the global report suite.

'Summary Data Sources' let you import pre-aggregated metrics into a true report suite in Adobe Analytics. Examples of 'Summary Data Sources' include metrics such as 'Offline Revenue' or 'Page Views" that occurred in another solution prior to your implementation of Adobe Analytics. Because Summary Data Sources uploads contain aggregated metrics, they cannot be segmented. Consequently, they do not appear segmented in virtual report suites.

Multi-suite tagging gives your organization the ability to import aggregated metrics at an individual report suite level. If Brand A wants to import offline revenue, it can do so separately from Brand B, and this data will appear in Brand A’s report suite. Brand B could do the same. If your organization uses or plans to use Summary Data Sources at a property, brand, region, etc. level, you may want to consider using multi-suite tagging instead of virtual report suites. 

## Steps to follow if you have decided to use VRS

After you have read through the considerations above and have decided to remove secondary server calls and use virtual report suites instead, here is what you need to do: 

**First**, create virtual report suites to match the data in your secondary/child report suites. Segment on a custom dimension such as “brand,” “platform,” “domain.” Pick a dimension that makes it easy to distinguish one digital property from another, and apply these segments to VRS.

* If you are migrating from an existing Adobe Analytics multi-suite tagging implementation, remember to compare the virtual report suites' segments to your existing child report suites before migrating your users. You want to ensure that the segments you are using in the virtual report suites are correct.

* If necessary, adjust the segments that the virtual report suites are based on.

* As a best practice, use [segment stacking](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) wherever possible so you can edit a segment in one location and have it apply to all virtual report suites that use that segment. For example, if I want to build one VRS for "mobile users from Europe," and another one for "mobile users from Asia," create one segment for mobile users and then separate segments for European and Asian users. This way, if you want to update the definition of your "mobile users" segment, you can do so in a single segment without needing to update each virtual report suite segment individually.

* You might be looking for mutually exclusive data sets in your virtual report suites. For example, you might want to see "Domain A" and "Domain B" as separate report suites, and you do not want any of Domain A's traffic in Domain B's report suite. In this case, use a "hit" container for your segments. 

**Second**, after you have confirmed that the virtual report suites you created are set up correctly and will meet your team's needs, remove the secondary report suite IDs from your implementation.

To remove secondary report suites:

* In Launch, hit the "x" next to any report suites you no longer wish to use.
* In DTM, locate the property and Adobe Analytics tool in question. In the Production Account ID and Staging Account ID fields, remove any report suite IDs that you no longer wish to use.
* In legacy JavaScript implementations, locate the `s.account` variable and remove any report suites that you no longer wish to use.

Leave only your global/parent report suite IDs to collect data from your sites and apps. In the Adobe Analytics interface, you can hide legacy report suites from your users by going to Admin > Company Settings.

If you are unable to edit your implementation, work with your Adobe account team. They can explore options for preventing your secondary server calls from being processed by Adobe Analytics.