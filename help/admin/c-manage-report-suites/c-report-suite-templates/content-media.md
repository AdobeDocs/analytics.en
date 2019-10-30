---
description: Defines common settings for a website that develops original content and displays articles and videos.
seo-description: Defines common settings for a website that develops original content and displays articles and videos.
seo-title: Content and Media
solution: Analytics
title: Content and Media
topic: Admin tools
uuid: 281b0bf8-59dc-46dc-b5d5-5e42827b785d
---

# Content and Media

Defines common settings for a website that develops original content and displays articles and videos.

|  Conversion Variables  | Type  | Subrelations  | Allocation  | Expiration  | `s_code` variable  |
|---|---|---|---|---|---|
|  Internal Campaign  | String  | Basic  | Most Recent (Last)  | Visit  | `evar1`  |
|  Internal Search Terms  | String  | Basic  | Most Recent (Last)  | Visit  | `evar2`  |
|  Commerce Variable 3  | String  | Basic  | Most Recent (Last)  | Visit  | `evar3`  |
|  Commerce Variable 4  | String  | Basic  | Most Recent (Last)  | Visit  | `evar4`  |

|  Success Events  | Type  | `s_code` variable  |
|---|---|---|
|  Registrations  | Counter (no subrelations)  | `event1`  |
|  Email Registrations  | Counter (no subrelations)  | `event2`  |
|  Subscriptions  | Counter (no subrelations)  | `event3`  |
|  Page Views  | Counter (no subrelations)  | `event4`  |
|  Ad Impressions  | Counter (no subrelations)  | `event5`  |
|  Ad Clicks  | Counter (no subrelations)  | `event6`  |

|  Custom Insight Variables  | `s_code` variable  |
|---|---|
|  Traffic Property 1 - 5  | `prop1, prop2, prop3, prop4, prop5`  |

The following table contains a list of the standard commerce events. Initial configuration for these events is identical in all report suite templates. Events with an s_code variable of N/A do not need to be set, they are provided automatically.

|  Standard Commerce Events  | Type  | `s_code` variable  |
|---|---|---|
|  Revenue  | Counter  | `purchase`  |
|  Orders  | Counter  | `purchase`  |
|  Units  | Counter  | `purchase`  |
|  Carts  | Counter  | `scOpen`  |
|  Cart Views  | Counter  | `scView`  |
|  Instances  | Counter  | N/A  |
|  Checkouts  | Counter  | `scCheckout`  |
|  Cart Additions  | Counter  | `scAdd`  |
|  Cart Removals  | Counter  | `scRemove`  |
|  Visits  | Counter (no subrelations)  | N/A  |
|  Page Views  | Counter (no subrelations)  | N/A  |
|  Daily Unique Visitors  | Counter (no subrelations)  | N/A  |
|  Unique Visitors  | Counter (no subrelations)  | N/A  |

