---
description: The number of times that a value was set for a variable.
keywords: instances
seo-description: The number of times that a value was set for a variable.
seo-title: Instances
solution: Analytics
title: Instances
topic: Metrics
uuid: ebf5a73d-7739-4cfb-b53e-790fa10b3960
index: y
internal: n
snippet: y
---

# Instances

The number of times that a value was set for a variable.

Instances are counted for all hit types, but are not counted when a value is recorded for a variable on a subsequent hit due to persistence.

For example, if a user arrives on your site via [!DNL example.com], the first image request on your site contains the referrer of [!DNL example.com]. When this value is set, one Instance is attributed to [!DNL example.com] even though this referrer is recorded for all pages viewed during that visit.

Instances for conversion variables in data warehouse were added mid-2011, allowing data warehouse requests to treat a specific conversion variable instance as a metric. These metrics are not available for reporting prior to the time they were introduced. 
