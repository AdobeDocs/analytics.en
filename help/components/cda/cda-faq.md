---
title: Cross-Device Analytics FAQ
description: Frequently asked questions for Cross-Device Analytics
---

# Frequently asked questions

**How can I use CDA to see how people move from one device type to another?**

You can use a Flow visualization with the Mobile Device Type dimension.

1. Log in to Adobe Analytics and create a new blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Mobile Device Type' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

**Can I see how people move between different user experiences (e.g. desktop browser vs. mobile browser vs. mobile app)?**

Using Mobile Device Type as illustrated above allows you to see how people move between mobile device types and desktop device types. However you may want to distinguish desktop browsers from mobile browsers. One way to do this is to create an eVar that records whether the experience occurred on a desktop browser, mobile browser, or mobile app. Then create a Flow diagram as described above, using your "experience" eVar rather than the Mobile Device Type dimension. This provides a slightly different view on cross-device behavior.

**How far back does CDA stitch visitors?**

* Adobe keeps device stitching data for approximately 30 days. If a device is intitially not identified by the Co-op Graph or Private graph, but is later identified within 30 days, CDA goes back and restates that device as belonging to identified person up to 30 days in the past. If some of a user's unidentified behavior falls outside the 30-day lookback window, that portion of the user's journey is not stitched.
* Adobe keeps device mappings in the Co-op Graph and Private Graph for approximately 6 months. An ECID that has no activity for more than six months is removed from the graph. Data already stitched in CDA is not affected, but subsequent hits for that ECID are treated as a new individual.

**How does CDA handle timestamped hits?**

Adobe treats timestamped hits as if they were received at the time of the timestamp, not when Adobe received the hit. Timestamped hits older than 1 month cannot be stitched, since they are considered outside the range Adobe keeps data used for stitching.
