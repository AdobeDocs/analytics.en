---
description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-title: Publish segments to the Experience Cloud
solution: Analytics
title: Publish segments to the Experience Cloud
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
---

# Publish segments to the Experience Cloud

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Recent updates have significantly optimized the publishing workflow. Previously, publishing a usable segment took approximately 48 hours. Now, processing can take up to 8 hours, but depending on other traffic and on the segment size, processing may be even faster. (However, we currently do not have a way to inform you when the segment is available, so you will have to check manually.) We have also increased the maximum number of publishable segments to 75 (from 20). You can view published segments in Components > Segments. 


## Prerequisites

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Otherwise you cannot publish it to the Experience Cloud.
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Creation] and the [!UICONTROL Segment Publishing] permissions to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## Considerations

* **Report Suite limits**: You can publish up to 75 segments per report suite. This limit is enforced. If you already have 75 segments published, you cannot publish any additional segments until you un-publish enough segments to get below the 75-segment threshold.
* **Membership limits**: Audiences shared to the [!DNL Experience Cloud] from Analytics cannot exceed 20 million unique members. 
* **Data Privacy**: Audiences are not filtered based on the authentication state of a visitor. If a visitor can browse your site in un-authenticated and authenticated states, actions that occur when a visitor is un-authenticated can still cause a visitor to be included in an audience. Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).
* In Analytics, you can edit or delete a published segment. If the segment is in use, a warning message is issued when you edit a segment. You cannot delete a published segment that is in use by Adobe [!DNL Target].

## Segment publishing timeline

|  What's available  | When it's available | Where it's available |
|---|---|---|
| Meta data (segment title and definition) | Immediately after publishing | [!DNL Audience Manager], [!UICONTROL Audience Library], [!DNL Target] |
| Usable segment with membership | ~ 8 hours after publishing | Visitor Profile Viewer in [!DNL Audience Manager] |
| Trait and membership population | within 24 hours | [!DNL Audience Manager] |

## Publish segments created in Analytics

1. Navigate to [!UICONTROL Analytics > Workspace > Components > Segments] > +
1. Create a segment in the [!UICONTROL Segment Builder]. 
1. Provide a title and a description for the segment - you won’t be able to save it otherwise.
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)].





## Unpublish segments

## View and manage segments in Analytics

