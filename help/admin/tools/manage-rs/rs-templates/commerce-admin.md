---
description: Defines common settings for an e-commerce website.
title: Commerce
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
---
# Commerce

Defines common settings for an e-commerce website.

|  Conversion Variables  | Type  | Subrelations  | Allocation  | Expiration  | `s_code` variable  |
|---|---|---|---|---|---|
|  Internal Promotions  | String  | Basic  | Most Recent (Last)  | Visit  | `evar1`  |
|  Internal Search Terms  | String  | Basic  | Most Recent (Last)  | Visit  | `evar2`  |
|  Merchandising Category  | String  | Basic  | Most Recent (Last)  | Visit  | `evar3`  |
|  Commerce Variable 4  | String  | Basic  | Most Recent (Last)  | Visit  | `evar4`  |
|  Commerce Variable 5  | String  | Basic  | Most Recent (Last)  | Visit  | `evar5`  |

|  Success Events  | Type  | `s_code` variable  |
|---|---|---|
|  Registrations  | Counter (no subrelations)  | `event1`  |
|  Custom Events 1-5  | Counter (no subrelations)  | `event1, event2, event3, event4, event5`  |

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
