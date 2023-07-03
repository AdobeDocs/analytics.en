---
title: How replays work
description: Understand the concept of "replay" in Cross-Device Analytics
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
---
# How replays work

Cross-Device Analytics makes two passes on data in a virtual report suite:

* **Live-stitching**: CDA attempts to stitch each hit as it comes in. Net new devices to the report suite that have never logged in are typically not stitched at this level. Devices already recognized are stitched immediately.
* **Replay**: Approximately once a week, CDA "replays" data based on unique identifiers it has learned. This stage is where new devices to the report suite become stitched.

## Example table

The following tables illustrate how both CDA methods ([Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md)) calculate the number of unique people:

### Live-stitching

As soon as a hit is collected, CDA attempts to stitch it to known devices. Consider the following example, where Bob uses two devices.

*Data as it appears the day it is collected:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | People metric (cumulative) using Device Graph | People metric (cumulative) using Field-based stitching |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob on his desktop computer, unauthenticated | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob logs in on his desktop | `1` (246) | `2` (246 and Bob) |
| `3` | `3579` | - | Bob on his mobile device, unauthenticated | `2` (246 and 3579) | `3` (246, Bob, and 3579) |
| `4` | `3579` | `Bob` | Bob logs in on mobile | `2` (246 and 3579) | `3` (246, Bob, and 3579) |
| `5` | `246` | - | Bob accesses your site on desktop again, unauthenticated | `2` (246 and 3579) | `3` (246, Bob, and 3579) |
| `6` | `246` | `Bob` | Bob logs in again via desktop | `2` (246 and 3579) | `3` (246, Bob, and 3579) |
| `7` | `3579` | - | Bob accesses your site again on mobile | `2` (246 and 3579) | `3` (246, Bob, and 3579) |
| `8` | `3579` | `Bob` | Bob logs in again via mobile | `2` (246 and 3579) | `3` (246, Bob, and 3579) |

Both unauthenticated and authenticated hits on new devices are counted as separate people (temporarily).

* **If using the device graph,** unauthenticated hits on recognized devices are live-stitched once a cluster is published by the device graph. Cluster publishing takes anywhere from three hours to two weeks.

  A third cumulative person is also added when a cluster is published. This third person represents the cluster itself, in addition to the individual devices. This third "person" remains until data is replayed.

  Attribution does not work across devices until after a cluster is published, and even then it only live-stitches from that point forward. In the example above, none of the hits are stitched across devices yet. Cross-device attribution on existing hits does not work until after replay stitching.
* **If using field-based stitching,** unauthenticated hits on recognized devices are live-stitched from that point forward.

  Attribution works as soon as the identifying custom variable ties to a device. In the example above, all hits except hits 1 and 3 are live-stitched (they all use the `Bob` identifier). Attribution works on hits 1 and 3 after replay stitching.

>[!NOTE]
>
>Timestamped hits older than 12 hours are not stitched in the live flow. However, these hits are included in Replay stitching, as long as they fall in the replay lookback window.

### Replay stitching

Replay occurs either daily or weekly, depending on how you requested CDA to be configured. During replay, CDA attempts to restate historical data within a defined lookback window:

* Daily replay uses a 1-day lookback window
* Weekly replay uses a 7-day lookback window.

If a device initially sends data while not authenticated and then logs in, CDA ties those unauthenticated hits to the correct person. The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data after replay:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | People metric (cumulative) using Device Graph | People metric (cumulative) using Field-based stitching |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob on his desktop computer, unauthenticated | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob logs in on his desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob on his mobile device, unauthenticated | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob logs in on mobile | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob accesses your site on desktop again, unauthenticated | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob logs in again via desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob accesses your site again on mobile | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob logs in again via mobile | `1` (Cluster1) | `1` (Bob) |
