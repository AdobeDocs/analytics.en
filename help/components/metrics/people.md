---
title: People
description: The number of unique individuals, typically with multiple devices.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
---
# People

There are two versions of the 'People' metric.
 
For members of the [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html) that do not use [Cross-Device analytics](../cda/overview.md), the 'People' metric is a statistically-derived count of the number of people represented in the report. It is the number of visitor IDs that are identified by the Device Co-op plus the number of devices that are not identified by the Co-op.
 
Within a [Cross-Device analytics](../cda/overview.md) virtual report suite, the 'People' metric is the sum of persons who have been identified in the report, plus the number of devices which have not been identified as belonging to a person.

In addition, depending on the reporting window a given person could be double counted. Meaning that if a given visitor has generated hits before and after the identification, that visitor will be counted as 1 unidentified people + 1 identified people.

To some extent, Replay service can fix the double counting by re-processing historical data in a given lookback window (configured).

You can also see a [descriptive example](unique-devices.md) of how 'People' metric works, together with 'Unique Devices' metric.