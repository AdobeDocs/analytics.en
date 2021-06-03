---
description: Analytics and Audience Manager both use segments. However, an Analytics segment is not exactly the same thing as an Audience Manager segment. These differences contribute, in part, to the discrepancies you will see in your Analytics and Audience Manager reports. As a result, it's important and useful to try and understand these differences when you start to work with segments in both of these solutions.
title: Understand segments in Analytics and Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
---
# Understand segments in Analytics and Audience Manager

Analytics and Audience Manager both use segments. However, an Analytics segment is not exactly the same thing as an Audience Manager segment. These differences contribute, in part, to the discrepancies you will see in your Analytics and Audience Manager reports. As a result, it's important and useful to try and understand these differences when you start to work with segments in both of these solutions.

## Audience Manager Segments {#section_417DC4B5648547778A27E42CE1D09900}

An&nbsp;Audience Manager&nbsp;segment is a group of visitors (user IDs) that qualify for a set of defined traits joined by logical rules. There are four criteria that determine if a visitor (user ID) is part of a segment in Audience Manager:

* Rules set on the segments themselves and the traits that make up each segment. These rules define the conditions a user ID has to meet or exhibit to be qualified for a segment.
* Algorithmic modeling. Users who qualify for a particular segment may qualify for other segments based on algorithmic modeling and analysis.
* Time-to-live (TTL) intervals. Segment membership can expire after a set interval or continue indefinitely.
* Recency and frequency. Defining when and how often users have an interaction (trait realization) can help create segments based the real (or perceived) level of interest in a site, section, or particular creative.

Audience Manager segment membership is fluid. Users can enter or drop out of a segment depending on whether they qualify for the segment criteria at the current point in time. This means the population of an&nbsp;Audience Manager&nbsp;segment can increase or decrease over time.

An Audience Manager segment is denoted as an audience in Analytics.

For more information, refer to [Trait and Segment Population Data in Segment Builder](https://experienceleague.adobe.com/docs/ audience-manager/user-guide/features/segments/segment-builder-data.html) and [Signals, Traits, and Segments](https://experienceleague.adobe.com/docs/ audience-manager/user-guide/reference/signal-trait-segment.html).

## Analytics Segments {#section_62EC584BB7134E10923BCBA7F9BD89A8}

An&nbsp;Analytics&nbsp;segment is a filtering mechanism for data in your reports. Filtering can occur at the visitor, visit, or hit level - rather than strictly at the visitor level as in Audience Manager. There are several important factors to consider when comparing an Analytics segment to an Audience Manager segment:

* Analytics segments operate on a different set of data than Audience Manager segments. During data collection, Analytics applies many different post-processing steps to the data that are not available to Audience Manager. Post-processing can include eVar persistence, processing rules, lookups (geo-location, mobile device), VISTA, and many others. Audience Manager receives pre-processed data through server-side forwarding (or DIL).

  Common data discrepancies occur when comparing segments based on dimensions that never expire in Analytics, to the same dimension in Audience Manager. For example, listVars or merchandising eVars that never expire.

  For example, if eVar = blue and is set to never expire in Analytics, any segment in Analytics with criteria "eVar = blue" will always include this visitor. Whereas, in Audience Manager, that visitor could fall out of a similarly defined segment after a set period of time.

* Analytics segments have more capabilities than AAM segments. Audience Manager segments are always evaluated at a visitor level. Analytics segments can be defined at a visitor, visit, or hit level (or a combination of these levels). Additionally, Analytics supports advanced segmentation capabilities that Audience Manager does not, such as sequential segmentation.
* As mentioned previously, Audience Manager visitors can enter or drop out of a segment depending on whether they qualify for the segment criteria at the current point in time.

  Conversely, in Analytics, visitors will be included or excluded from a segment based on the reporting date range. For example, a single visitor made a purchase last month. In AAM, that visitor would be included in a "purchaser" segment, regardless of the date range. In Analytics, a report based on this month would not include the visitor in the segment. However, a report based on this month & last month would include the visitor in the segment.

See the [Analytics Segmentation Guide](https://experienceleague.adobe.com/docs/ analytics/components/segmentation/seg-home.html) for more information.
