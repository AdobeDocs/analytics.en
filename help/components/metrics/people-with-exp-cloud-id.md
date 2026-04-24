---
title: People with Experience Cloud ID
description: The number of people in Cross-Device Analytics who have an Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# People with Experience Cloud ID

'People with Experience Cloud ID' is a [Cross-device analytics](../cda/overview.md) metric that shows the number of [People](people.md) who were identified by Adobe using the [Experience Cloud ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## How this metric is calculated

Considering each [People](people.md) (identified or unidentified), this [metric](overview.md) increases if the hit contains the `mid` query string (based on the [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

You can create the calculated metric `[People with ECID] ÷ [People]` to obtain the percent of visitors to your site using the ID service.

See the equivalent non-CDA metric [Visitors with Experience Cloud ID](visitors-with-ecid.md) for more information around importance of Experience Cloud ID and debugging your setup.
