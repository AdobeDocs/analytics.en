---
title: Cross-Device Analytics FAQ
description: Frequently asked questions for Cross-Device Analytics
---

# Frequently asked questions

**How can I use CDA to see how visitors move from one device to another?**

You can use a Flow visualization with the Mobile Device Type dimension.

1. Log in to Adobe Analytics and create a new blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Mobile Device Type' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

**How far back does CDA stitch visitors?**

* Adobe keeps device stitching data for approximately 30 days. Devices that Adobe identifies the same are stitched during this period. If a visitor lets more than a month pass between two un-stitched devices, those devices are not stitched.
* Adobe keeps device mappings for approximately 6 months. An ECID identifying an individual expires if it is inactive for more than 6 months. Subsequent hits for that ECID are treated as a new individual.

**How does CDA handle timestamped hits?**

Adobe treats timestamped hits as if they were received at the time of the timestamp, not when Adobe received the hit. Timestamped hits older than 1 month cannot be stitched, since they are considered outside the range Adobe keeps data used for stitching.
