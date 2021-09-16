---
title: People with Experience Cloud ID
description: The number of people in Cross-Device Analytics who have an Experience Cloud ID.
---
# People with Experience Cloud ID

'People with Experience Cloud ID' is a [Cross-device analytics](../cda/overview.md) metric that shows the number of [People](people.md) who were identified by Adobe using the [Experience Cloud ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## How this metric is calculated

Considering each [People](people.md) (identified or unidentified), this metric increases if the hit contains the `mid` query string (based on the [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

You can create the calculated metric `[People with ECID] ÷ [People]` to obtain the percent of visitors to your site using the ID service.

See the equivalent non-CDA metric [Visitors with Experience Cloud ID](visitors-with-ecid.md) for more information around importance of Experience Cloud ID and debugging your setup.
