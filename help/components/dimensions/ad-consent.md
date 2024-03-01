---
title: Ad Consent
description: See the configuration for advertising consent for third-party ad providers.
feature: Dimensions
---
# Ad Consent

The 'Ad Consent' [dimension](overview.md) displays whether consent is collected to send data to third-party advertising providers, like Google, Meta, and others.

Currently, this dimension is used for Google only. Due to European privacy regulations, Google is requiring that data sent to their servers and collected in Europe must indicate whether consent is collected. Some Analytics customers send event data via Adobe Advertising as conversion events to Google.

In the future, this dimension can be used to support encoding additional consent information for other third-party advertising providers.


## Populate this dimension with data

This dimension collects data from the following [Context data variables](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`
  
You populate the context data variable with the relevant value. The first character of the value represents the states that Google requires when receiving data from Adobe Analytics via Adobe Advertising:

| Value of first character| Explanation |
|:-:|---|
| `"Y..."` | Grant consent to Google to use the data for advertising. |
| `"N..."` | Grant no consent to Google to use data for advertising. |
| `"U..."` | Unknown or unspecified. |
| `"-..."` | You are not using Google for advertising and decide explicity not to specify a value |

Your organization determines the logic to implement this context data variable. The value does not persist beyond the hit it is set on, so you must set the context data variable on each page.
