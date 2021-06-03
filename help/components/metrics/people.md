---
title: People
description: The number of unique individuals, typically with multiple devices.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
---
# People

There are two versions of the 'People' metric.
 
For members of the [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html) that do not use [Cross-Device analytics](../cda/overview.md), the 'People' metric is a statistically-derived count of the number of people represented in the report. It is the number of visitor IDs that are identified by the Device Co-op plus the number of devices that are not identified by the Co-op.
 
Within a [Cross-Device analytics](../cda/overview.md) virtual report suite, the 'People' metric is a direct count of unique individuals instead of a statistical derivation. The definition of a person in CDA is based on either the Device Co-op, Private Graph, or field-based stitching, depending on how CDA is configured for the base report suite. People is the sum of individuals who have been identified in the report, plus the number of devices which have not been identified as belonging to a person.
