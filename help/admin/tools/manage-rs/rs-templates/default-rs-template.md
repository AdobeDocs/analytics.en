---
description: Configures several common variables and success events for a typical website.
title: Default template
feature: Report Suite Settings
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
exl-id: 36aaded4-5c46-41af-a5c6-216bd2fcadb2
TQID: https://experienceleague.adobe.com/Tz2kROFW9n8apieb-bLIEPJ26LsZIhci5Azf1dvxRLI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Default template

Configures several common variables and success events for a typical website.

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
