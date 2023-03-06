---
description: Virtual report suites and multi-suite tagging have different advantages. Learn which is best for your organization.
keywords: Virtual Report Suite,VRS
title: Virtual report suites and multi-suite tagging considerations
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
---
# Virtual report suites and multi-suite tagging considerations

Virtual report suites (VRS) let you view data from a report suite that is collecting data from your digital properties, but with a segment permanently applied.

In many cases, you can use virtual report suites to replace multi-suite tagging. Switching to virtual reports suites can effectively remove the necessity for [secondary server calls](/help/admin/admin/c-server-call-usage/overage-overview.md). For example, your organization has 6 different websites, each sending data to their own report suite as well as a combined global report suite. Each site incurs a secondary server call; one to the individual brand report suite, and a second to the global report suite. Instead, you can send data from all sites solely to the global report suite, then use multiple virtual report suites to separate each brand.

Replacing multi-suite tagging with a global report suite and VRS allows you to simplify your Adobe Analytics implementation and reduce server call consumption, and is encouraged as a best practice. However, there are some important limitations of VRS to consider. The following guidelines can help you decide whether implementing virtual report suites built on a global report suite is the right approach for you.

## Guidelines

If you are unsure whether the use cases described apply to you and your organization, consult your other Adobe Analytics administrators or your Adobe Account Team. They can help assess your business needs and make a recommendation.

Take the following considerations into mind when determining if you should use multi-suite tagging or virtual report suites:

### Publishing segments to the Adobe Experience Cloud

Sharing segments to Adobe Experience Cloud is not supported for virtual report suites. Users who want to share a segment to the Experience Cloud must have access to the source report suite.

Segments cannot yet be published to Adobe Experience Cloud from a virtual report suite for personalization and targeting. All users who publish segments need access to the source report suite for this purpose. For example, you want users to only have access to data for their geographical regions only, but you want them to be able to create and share segments from Adobe Analytics to Adobe Experience Cloud for targeting in Adobe Target. In this case, Adobe recommends using multi-suite tagging. If you don't mind users having access to the global report suite or you do not need to publish segments for use in other solutions, virtual report suites can be used.

### Real-time and current data

Real-time reports are not supported in virtual report suites, because the data is segmented. Current data is also not supported in virtual report suites, as it does not support segmentation. Both of these features are specific to Reports & Analytics.

[Real-time reports](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md) and [Current Data](/help/technotes/latency.md) are not available in virtual report suites. This affects users who respond to trends seen in Reports & Analytics within seconds or a few minutes of data collection. For example, this could include editors in a newsroom who adjust headlines based on real-time content consumption. Consider using multi-suite tagging if you have significant real-time data needs specific to individual report suites. Real-time and current data can still be used on the global report suite.

### Unique limits

If you have a global report suite that combines a large number of sites together, it is possible that you run into the [low-traffic](/help/technotes/low-traffic.md) line item frequently. If you use multi-suite tagging, this is only an issue for the global report suite (individual report suites would be less likely to see low-traffic). If you use virtual report suites, unique limits are shared, causing individual report suites to show low-traffic as well. Consider using multi-suite tagging if you want to avoid bucketing data into low-traffic.

For example, a large media organization owns 100 web properties. Each property publishes a few thousand news articles monthly, in addition to hosting all articles from previous months. This organization uses a global report suite where eVar1 is 'Article Name'. In this report, there are approximately 4 million unique article names each month from the various properties combined. If using a virtual report suite, the top 500,000 values that comprise the bulk of the traffic are included in virtual report suites; the remaining 3.5 million are included under low-traffic. If multi-suite tagging is used, each individual report suite can see its own top 500k values. The global report suite unique limits is the same between using multi-suite tagging and virtual report suites.

Adobe Customer Care can increase unique value limits for a small number of dimensions, which can eliminate this problem entirely. Consult your account team and Customer Care for more information.

### Shared variables across report suites

Virtual report suites do not have their own sets of dimensions and metrics; they inherit these from their source report suite. The global report suite must capture all dimensions and metrics for all websites. Report suites currently have a maximum of 250 eVars and 1000 custom events.

Different site have different implementation needs. Some dimensions and events can be shared between two sites. For example, an email registration can use the same event on multiple websites, triggering the same custom event. Other dimensions might be specific to a site. For example, only one of your sites has the ability for the user to change their profile picture. This custom event would only be implemented on the website that supports it.

Make sure that the number of unique dimensions and metrics can fit in a single global report suite. If you find that there are too many unique dimensions or metrics, review each dimension within each implementation. There is likely overlap and dimensions that are not critical to business success. Consider using [classifications](/help/components/classifications/c-classifications.md) as well. For example, instead of capturing 'Product Name' in eVar5, create a 'Product Name' classification based on the 'Product' dimension. Classifications in a source report suite are automatically available to any dependent virtual report suites.

>[!TIP]
>
>With the introduction of [curation](/help/analyze/analysis-workspace/curate-share/curate.md), you can change the name of a given dimension or metric on a per-VRS basis.

### Segmentation nuances

A virtual report suite on a fundamental level is simply a segment applied to a report suite. Visit and visitor-based dimensions can provide unintuitive reporting results.

For example, you have two websites, A and B, both sending data into a global report suite. Some visitors inevitably cross over from site A to site B, and this movement from one to the other is visible in pathing in the global report suite. If you build virtual report suites for sites A and B, a visit that started on site A and ended on site B wouldn't show an entry page in VRS B. The entry page for this visit began on site A, which is segmented out of the virtual report suite.

### Currency conversion

Virtual report suites do not report on a different currency than the report suite on which they are based. Adobe Analytics does allow you to convert currency when running reports, but the exchange rate is based on the current day (even for historical data).

If your organization does their analysis in a single currency, this is not cause a problem. However, if you have a significant business need for different regional teams who need to view revenue in their own local currency, consider using multi-suite tagging.

### Data feeds

Data Feeds cannot use virtual report suites. However, you can receive a data feed from a global report suite then separate it.

Data Feeds let you receive a daily or hourly export of all of your Adobe Analytics data at an individual hit level. Data Feeds cannot be pre-segmented before they are delivered to you, so you can only receive a data feed for your global report suite. If your organization has a strong need for individual data feeds at a brand, property, region, or other granular level, consider using multi-suite tagging.

### Data connectors with partner accounts

Certain Adobe partner integrations into Adobe Analytics are limited to one partner account per report suite. Some organizations might require multiple partner accounts for the same integration.

For example, only one Google DCM is allowed per report suite. Many companies have multiple DCM accounts, which allows different brands, business units, and regions to manage their displays ads separately from one another. Integrations cannot be set up in virtual report suites. If you have dependent data connectors with multiple accounts, consider using multi-suite tagging.

### Summary data sources

Summary data sources let you import aggregated metrics into Adobe Analytics at a report-suite level. Because summary data source uploads contain aggregated metrics *without a visitor ID*, they cannot be segmented in [!UICONTROL Visit] and [!UICONTROL Visitor] containers. Since VRS operates using segmentation, data imported using summary data sources will not be not available in virtual report suites if the segment is built using a Visit or Visitor container.

Summary data sources show up in the virtual report suite if a Hit container is used and if that Hit container has rules conditioned to include the data source information.

>[!TIP]
>
>Full processing data sources support segmentation, and can be used in virtual report suites.

## Steps to follow if you have decided to use VRS

If you opt to remove secondary server calls in favor of virtual report suites:

1. Create virtual report suites to match the data in your child report suites. Segment on a custom dimension that distinguishes your sites from each other.
   * If you migrate from an existing multi-suite tagged implementation, compare the virtual report suite's segments to your existing child report suites. You will want to make sure the data is comparable before moving users to the virtual report suite.
   * As a best practice, consider using [segment stacking](/help/components/segmentation/segmentation-workflow/seg-build.md) so you can edit a segment in one location and have it apply to all dependent virtual report suites.
   * Use hit containers if you want to keep virtual report suites more mutually exclusive.
2. After you have confirmed that the virtual report suites are set up correctly, remove the secondary report suite ID's from your implementation. To remove secondary report suites:
   * In the Adobe Analytics extension within Adobe Experience Platform Data Collection, click the 'x' next to any report suites that you don't want to use anymore.
   * In legacy JavaScript implementations, locate the `s.account` variable and remove any report suite ID's that you don't want to use anymore.
   * In all cases, leave only the global/parent report suite ID to collect data for your sites and apps.
   * Navigate to Admin > Report Suites and hide any secondary report suites no longer used.
