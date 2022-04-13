---
title: Cross-device visitor identification FAQ
description: Frequently asked questions for cross-device visitor identification
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
---
# Cross-device visitor identification FAQ

Frequently asked questions for cross-device visitor identification.

**What is the difference between cross-device visitor identification and Cross-Device Analytics?**

Cross-device visitor identification uses the `visitorID` variable to tie devices together, with several major limitations. One of the biggest limitations of this identification method is that unauthenticated hits are isolated unless the device has already been recognized. These unauthenticated hits can inflate your unique visitor counts.

Cross-Device Analytics is Adobe's latest cross-device visitor identification method. It uses the Experience Cloud ID service and device graph to retroactively stitch visits from different devices together. CDA requires the use of the `setCustomerIDs` function to determine which devices are used by the same visitor.

**How does cross-device visitor identification handle segments?**

Cross-device visitor identification treats segments similarly to other capabilities. It looks at each individual hit to see if it matches the segment criteria, and includes those hits in your data if it matches. Segments using visit and visitor-based containers still look at the visitor ID. Make sure your implementation uses the `visitorID` variable wherever possible to consistently identify unique visitors for segmentation.
