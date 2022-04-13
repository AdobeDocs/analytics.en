---
description: Learn how to implement multi-suite tagging to send image request to multiple report suites.
title: Implementing multi-suite tagging
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
---
# Implementing multi-suite tagging

[Multi-suite tagging](/help/admin/c-manage-report-suites/rollup-report-suite.md) allows you to send image requests not only to a global report suite but also to individual child report suites so that you can provide subsets of your company's global report suite data to different end users.

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
 
 To understand if virtual report suites are your best approach, see "[Virtual report suites and multi-suite tagging considerations](/help/components/vrs/vrs-considerations.md)." See also "[Virtual Report Suites vs. Multisuite Tagging](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)" for a comparison of multi-suite tagging and virtual report suite functionality.
