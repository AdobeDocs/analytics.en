---
title: People with Experience Cloud ID
description: The number of people in Cross-Device Analytics who have an Experience Cloud ID.
---
# People with Experience Cloud ID

'People with Experience Cloud ID' is a [Cross-device analytics](../cda/overview.md) metric that shows the number of [People](people.md) who were identified by Adobe using the [Experience Cloud ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## How this metric is calculated

Considering each [People](people.md) (identified or unidentified), this metric will increment if there are corresponding hits using the `mid` query string (based on the [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

Based on 'People with Experience Cloud ID' and 'People' metrics, there is the 'Experience Cloud ID coverage' that can tell the percent of visitors to your site using the ID service.

To read more about the importance of Experience Cloud ID and debugging your setup, please see the equivalent non-CDA metric [Visitors with ECID](visitors-with-ecid.md).