---
description: Defines common settings for a website that aggregates content, such as a news portal.
title: Aggregator portal
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
TQID: https://experienceleague.adobe.com/rH1TSHrMMKxFtMlv0GR-UKF-OJk8SBbt1pq92DYhgVk
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
# Aggregator portal

Defines common settings for a website that aggregates content, such as a news portal.

|  Conversion Variables  | Type  | Subrelations  | Allocation  | Expiration  | `s_code` variable  |
|---|---|---|---|---|---|
|  Internal Campaign  | String  | Basic  | Most Recent (Last)  | Visit  | `evar1`  |
|  Internal Search Terms  | String  | Basic  | Most Recent (Last)  | Visit  | `evar2`  |
|  Referral Category  | String  | Basic  | Most Recent (Last)  | Visit  | `evar3`  |

|  Success Events  | Type  | `s_code` variable  |
|---|---|---|
|  Sign-in  | Counter (no subrelations)  | `event1`  |
|  Referral View  | Counter (no subrelations)  | `event2`  |
|  Referral Clicks  | Counter (no subrelations)  | `event3`  |

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
