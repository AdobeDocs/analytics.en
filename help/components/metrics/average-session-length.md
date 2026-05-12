---
title: Average session length (mobile)
description: The average session length for the mobile device.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
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
# Average session length (mobile)

The 'Average session length (mobile)' [metric](overview.md) shows the average amount of time a given dimension item is present per dimension item. It is similar to the [[!UICONTROL Time spent per visit (seconds)]](time-spent-per-visit.md) metric, except this metric uses mobile SDK-specific components as part of its calculation.

## How this metric is calculated

This metric is calculated using the [Lifecycle metrics](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
