---
title: People
description: The number of unique individuals, typically with multiple devices.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
---
# People

>[!IMPORTANT]
>
>The People metric that relates to the Device Co-op will be deprecated on March 8, 2023. The CDA-related People metric that is described below is not affected by this deprecation.

The 'People' metric is specific to [Cross-Device Analytics](../cda/overview.md) virtual report suites. It represents the sum of individuals who are identified in the report, plus the number of devices that are not identified as belonging to a person.

If a visitor is identified mid-visit, that visitor can count as 2 People (1 unidentified person and 1 identified person). [Replay](/help/components/cda/replay.md) mitigates this double counting depending on the reporting window, replay frequency, and success rate. See [Unique devices](unique-devices.md) for more information.
