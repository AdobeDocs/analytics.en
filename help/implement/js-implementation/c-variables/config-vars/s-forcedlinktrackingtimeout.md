---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---


# s.forcedLinkTrackingTimeout

This value specifies the maximum wait time. Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. If the track link call completes before this timeout, the `doneAction` is executed immediately. If you notice that track link calls are not completing, you might need to increase this timeout.

Default Value = 250

Example: `s.forcedLinkTrackingTimeout = 500`
