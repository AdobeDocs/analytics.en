---
title: Hit type
description: Determines if the hit was a foreground or background hit.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
---
# Hit type

The 'Hit type' dimension determines if a mobile app was in the foreground or background when the hit was sent to Adobe data collection servers. This dimension is only relevant to report suites that contain data for mobile applications. Browser data collected through AppMeasurement always reports the hit as "Foreground".

## Populate this dimension with data

This dimension works out of the box for all mobile SDK implementations on version 4.13.6 or higher. If you do not use the mobile SDK, all hits list under the "Foreground" dimension item. If "Disable Legacy Reporting and Attribution for Background Hits" is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Dimension items

Dimension items include `"Foreground"` and `"Background"`. Any hit that was not sent in the background of a mobile application belongs to the `"Foreground"` dimension item. Any hit sent where the mobile application was in the background belongs to the `"Background"` dimension item.
