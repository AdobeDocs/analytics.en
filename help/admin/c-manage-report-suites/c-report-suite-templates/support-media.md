---
description: Provides common settings for a website that provides product support articles and videos.
title: Support Media
feature: Report Suite Settings
exl-id: f522173a-8f58-4fa4-868b-251158a71e26
---
# Support Media

Provides common settings for a website that provides product support articles and videos.

|  Conversion Variables  | Type  | Subrelations  | Allocation  | Expiration  | `s_code` variable  |
|---|---|---|---|---|---|
|  Internal Promotion  | String  | Basic  | Most Recent (Last)  | Visit  | `evar1`  |
|  Internal Search Terms  | String  | Basic  | Most Recent (Last)  | Visit  | `evar2`  |
|  Self-Service Event Type  | String  | Basic  | Most Recent (Last)  | Visit  | `evar3`  |

No success events are configured by this report suite template.

|  Custom Insight Variables  | `s_code` variable  |
|---|---|
|  Secure / Non-Secure  | `prop1`  |
|  Traffic Property 2 - 5  | `prop2, prop3, prop4, prop5`  |

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
