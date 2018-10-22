---
description: The number of times a given value is captured as the last value in a visit. Exits can occur only once per visit.
seo-description: The number of times a given value is captured as the last value in a visit. Exits can occur only once per visit.
seo-title: Exits
solution: Analytics
title: Exits
topic: Metrics
uuid: e74296f6-ea89-4857-b201-a50f95a4f052
index: y
internal: n
snippet: y
---

# Exits

The number of times a given value is captured as the last value in a visit. Exits can occur only once per visit.

Exit pages have a visit breakdown scope, meaning they persist across all hits for a visit. See [Breakdown and segmentation containers](http://marketing.adobe.com/resources/help/en_US/sc/user/?f=c_Breakdown_and_segmentation_containers) for more information.

When applied to a dimension, Exits are counted on the last value of a visit, which may happen on any hit during the visit. If there is no value on the last hit, the Exit is attributed to the most recent value.

If an exit occurs outside the reporting range for a visit inside the reporting range, it will be included as long as it is not along a month boundary (inside the dataset). 
