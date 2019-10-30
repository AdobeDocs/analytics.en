---
description: null
keywords: Data Feed;job;visitors;Experience Cloud ID;analytics visitor id;identify
seo-description: null
seo-title: Identify visitors
solution: Analytics
title: Identify visitors
topic: Reports and analytics
uuid: 2490b67e-a333-422d-82fa-cb0670ef2e0c
---

# Identify visitors

Analytics provides several mechanisms by which visitors can be identified (listed in [Identifying Visitors](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**To identify unique visitors:**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5, 8, and 9 are summary rows uploaded using data sources. 7 represents transaction ID data source uploads that should not be included in visit and visitor counts. See [Hit Source Lookup](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42) 
1. Combine `post_visid_high` with `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

If you would like to determine which mechanism was used to determine the visitor ID value (for example, to calculate cookie acceptance), the `post_visid_type` contains a lookup key that indicates which ID method was used. The lookup keys are listed along with the visitor ID mechanisms in the [table below](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

The Experience Cloud ID is reported in a separate column, `mcvisid`. Because this ID is reported in its own column, it can be unclear if Analytics is using this ID or a different ID to identify a visitor.

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. These fields are the only visitor ID fields guaranteed to have a value with every row in the data feed.

## Analytics Visitor IDs {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

There are several ways a visitor can be identified in Analytics (listed in the following table in order of preference): 

|  Order Used  | Query Parameter (collection method)  | post_visid_type column value  | Present When |
|---|---|---|---|
|   ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html)  | 0  | s.visitorID is set.| 
|   ![](assets/step2_icon.png) | [aid (s_vi cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_analytics.html)  | 3  |Visitor had an existing s_vi cookie before you deployed the Visitor ID service, or you have a Visitor ID [grace period](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html) configured. |
|   ![](assets/step3_icon.png) | [mid (AMCV_ cookie set by Identity Service)](https://marketing.adobe.com/resources/help/en_US/mcvid/)  | 5  | Visitor's browser accepts cookies (first-party), and the Identity Service is deployed.  |
|   ![](assets/step4_icon.png) | [fid (fallback cookie on H.25.3 or newer, or AppMeasurement for JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html)  | 4  | Visitor's browser accepts cookies (first-party).  |
|   ![](assets/step5_icon.png) | [HTTP Mobile Subscriber header](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_mobile.html)  | 2  | Device is recognized as a mobile device.  |
|   ![](assets/step6_icon.png) | [IP Address, User Agent, Gateway IP Address](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html)  | 1  | Visitor's browser does not accept cookies.  |

In many scenarios you might see 2 or 3 different IDs on a call, but Analytics will use the first ID present from that list as the official visitor ID, and split that value across the `post_visid_high` and `post_visid_low` columns. For example, if you are setting a custom visitor ID (included in the "vid" query parameter), that ID will be used before other IDs that might be present on that same hit.
