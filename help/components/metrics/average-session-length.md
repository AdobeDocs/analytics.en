---
title: Average session length (mobile)
description: The average session length for the mobile device.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
---
# Average session length (mobile)

The 'Average session length (mobile)' [metric](overview.md) shows the average amount of time a given dimension item is present per dimension item. It is similar to the [Time spent per visit [seconds]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) metric, except this metric uses mobile SDK specific components as part of its calculation.

## How this metric is calculated

This metric is calculated using the [Lifecycle metrics](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Session length' / ('Launches' - 'First launches'`.
