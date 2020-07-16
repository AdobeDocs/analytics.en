---
title: How replays work
description: Understand the concept of "replay" in Cross-Device Analytics
---

# How replays work

Cross-device Analytics makes two passes on data in a virtual report suite:

* **Live stitching**: CDA attempts to stitch each hit as it comes in. Net new devices to the report suite are typically not deduplicated at this level. Devices already recognized are stitched immediately.
* **Replay**: Approximately once a week, CDA "replays" data based on unique identifiers it has learned. This stage is where new devices to the report suite become deduplicated.

## Example table

The following tables illustrate how both CDA methods ([Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md)) calculate the number of unique people:

### Live stitching

As soon as a hit is collected, CDA attempts to stitch it to known devices.

*Data as it appears the day it is collected:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | Device graph pseudo-identifier | Device graph People metric (cumulative) | Field-based stitching pseudo-identifier | Field-based stitching People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 246 | - | Bob on his desktop computer, unauthenticated | 246 | 1 | 246 | 1 |
| 2 | 246 | Bob | Bob logs in on his desktop | 246 | 1 | Bob | 2 |
| 3 | 3579 | - | Bob on his mobile device, unauthenticated | 3579 | 2 | 3579 | 3 |
| 4 | 3579 | Bob | Bob logs in on mobile | 3579 | 2 | Bob | 3 |
| 5 | 246 | - | Bob accesses your site on desktop again, unauthenticated | 246 | 2 | Bob | 3 |
| 6 | 246 | Bob | Bob logs in again via desktop | 246 | 2 | Bob | 3 |
| 7 | 3579 | - | Bob accesses your site again on mobile | 3579 | 2 | Bob | 3 |
| 8 | 3579 | Bob | Bob logs in again via mobile | 3579 | 2 | Bob | 3 |

Note that both unauthenticated and authenticated hits on new devices are counted as new people (temporarily). However, CDA stitches unauthenticated hits to the device live from that point forward.

### Replay stitching

Approximately once a week, CDA recalculates historical data based on devices it now recognizes. If a device initially sends data while not authenticated and then logs in, CDA ties those unauthenticated hits to the correct person. The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data 1 week later:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | Device graph pseudo-identifier | Device graph People metric (cumulative) | Field-based stitching pseudo-identifier | Field-based stitching People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 246 | - | Bob on his desktop computer, unauthenticated | Cluster1 | 1 | Bob | 1 |
| 2 | 246 | Bob | Bob logs in on his desktop | Cluster1 | 1 | Bob | 1 |
| 3 | 3579 | - | Bob on his mobile device, unauthenticated | Cluster1 | 1 | Bob | 1 |
| 4 | 3579 | Bob | Bob logs in on mobile | Cluster1 | 1 | Bob | 1 |
| 5 | 246 | - | Bob accesses your site on desktop again, unauthenticated | Cluster1 | 1 | Bob | 1 |
| 6 | 246 | Bob | Bob logs in again via desktop | Cluster1 | 1 | Bob | 1 |
| 7 | 3579 | - | Bob accesses your site again on mobile | Cluster1 | 1 | Bob | 1 |
| 8 | 3579 | Bob | Bob logs in again via mobile | Cluster1 | 1 | Bob | 1 |

Note that the device graph uses clusters (groups of devices that it recognizes as the same person). Field-based stitching uses the string value in eVar1.

## Recap

* Data less than a week old immediately stitches known devices, but does not immediately stitch new or unrecognized devices
* Data more than a week old is replayed, and changes historical data based on devices it has learned to identify
