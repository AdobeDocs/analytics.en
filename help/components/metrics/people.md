---
title: People
description: The number of unique individuals, typically with multiple devices.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
TQID: https://experienceleague.adobe.com/wakgq--xWCQqF-CONFhD9A-UK8m4insevQO-YafphQ0
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# People

>[!IMPORTANT]
>
>The People metric that relates to the Device Co-op is deprecated as of March 8, 2023. The CDA-related People metric described on this page is still active.

The 'People' [metric](overview.md) is specific to [Cross-Device Analytics](../cda/overview.md) virtual report suites. It represents the sum of individuals who are identified in the report, plus the number of devices that are not identified as belonging to a person.

If a visitor is identified mid-visit, that visitor can count as 2 People (1 unidentified person and 1 identified person). [Replay](/help/components/cda/replay.md) mitigates this double counting depending on the reporting window, replay frequency, and success rate. See [Unique devices](unique-devices.md) for more information.
