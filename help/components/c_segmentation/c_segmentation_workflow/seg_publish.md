---
description: Lets you use the segment for marketing activity in the Audience library, Target, and Audience Management.
seo-description: Lets you use the segment for marketing activity in the Audience library, Target, and Audience Management.
seo-title: Publish segments to the Experience Cloud
solution: Analytics
title: Publish segments to the Experience Cloud
topic: Segments
uuid: 9b25f593-6716-4175-93bc-d8364958410d
index: y
internal: n
snippet: y
---

# Publish segments to the Experience Cloud

Lets you use the segment for marketing activity in the Audience library, Target, and Audience Management.

This check box in the Segment Builder appears only if the report suite that you are saving this segment to is [enabled for the Experience Cloud](http://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the Audience library, Target, and Audience Manager. A segment title and description are required. 

>[!NOTE]
>
>In Analytics, you can edit or delete a published segment. If the segment is in use, a warning message is issued when you edit a segment. You cannot delete a published segment that is in use by Adobe Target.

>[!IMPORTANT]
>
>You should limit the number of audiences shared from Analytics to 20 (per customer/Experience Cloud organization) to avoid impacts on latency and data availability. Audiences shared to the Experience Cloud from Analytics should not exceed 20 million unique visitors. Also, due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud.

>[!IMPORTANT]
>
>Once a visitor qualifies for the audience shared from Analytics, there is a 24 - 48 hour delay before that information is actionable in Target, Media Optimizer, and Campaign.

