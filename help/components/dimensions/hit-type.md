---
title: Hit type
description: Determines if the hit was a foreground or background hit.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Hit type

The 'Hit type' [dimension](overview.md) determines if a mobile app was in the foreground or background when the hit was sent to Adobe data collection servers. This dimension is only relevant to report suites that contain data for mobile applications. Browser data collected through AppMeasurement always reports the hit as `"Foreground"`.

## Populate this dimension with data

This dimension works out of the box for all mobile SDK implementations on version 4.13.6 or higher. The mobile SDK sets the [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) variable (the `cp` query parameter) to indicate whether each hit occurred in the foreground or background. If you do not use the mobile SDK, all hits list under `"Foreground"`. If **[!UICONTROL Prevent background hits from starting a new visit]** is selected when configuring a [Virtual report suite](../vrs/vrs-mobile-visit-processing.md), background hits do not inflate [[!UICONTROL Visits]](../metrics/visits.md) and [[!UICONTROL Unique visitors]](../metrics/unique-visitors.md).

## Dimension items

Dimension items include `"Foreground"` and `"Background"`. Background hits only occur on mobile devices where the tracked application is in the background.
