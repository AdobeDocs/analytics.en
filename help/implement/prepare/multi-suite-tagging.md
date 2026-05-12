---
description: Learn how to implement multi-suite tagging to send image request to multiple report suites.
title: Implementing multi-suite tagging
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/djrzQEjvc--wnh2wR1HNV-LVEn6RPcyiaLKLha5pfSY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Implementing multi-suite tagging

[Multi-suite tagging](/help/admin/tools/manage-rs/rollup-report-suite.md) allows you to send image requests not only to a global report suite but also to individual child report suites so that you can provide subsets of your company's global report suite data to different end users.

To implement multi-suite tagging, you must include the Report Suite ID (RSID) for the global report suite and also the RSIDs for the applicable child report suites in the tracking code for your webpages and apps.

* For Adobe Experience Platform tags implementations, specify each of the report suites for the [[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

* For legacy JavaScript and mobile SDK implementations, separate the RSIDs with commas and no spaces (`rsid1,rsid2,rsid3` and so on).

* For other implementation types, use the required syntax to list multiple RSIDs.

>[!TIP]
>
> The best practice is to list the global report suite or report suite ID first.

Multi-suite tagging incurs multiple server calls for each image request: a primary call to the global report suite and a secondary call for each child report suite.

>[!NOTE]
>
> [Virtual report suites](/help/components/vrs/vrs-about.md), which also allow you to provide subsets of your company's global report suite data to different end users, do not incur secondary server calls.

## Should I implement multi-suite tagging or virtual report suites?

 Using virtual report suites instead of multi-suite tagging is often a best practice, but your business needs determine the best report suite approach for your organization.
 
 To understand if virtual report suites are your best approach, see "[Virtual report suites and multi-suite tagging considerations](/help/components/vrs/vrs-considerations.md)." See also "[Virtual report suites vs. ,multi-suite tagging](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)" for a comparison of multi-suite tagging and virtual report suite functionality.
