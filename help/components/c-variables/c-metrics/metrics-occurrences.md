---
description: The number of times a specific value is captured, plus the number of page views for which the given value persisted. In other words, Occurrences are sum of page views and page events. Occurrences are available in Analysis Workspace and in Ad Hoc Analysis.
seo-description: The number of times a specific value is captured, plus the number of page views for which the given value persisted. In other words, Occurrences are sum of page views and page events. Occurrences are available in Analysis Workspace and in Ad Hoc Analysis.
seo-title: Occurrences
solution: Analytics
title: Occurrences
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
---

# Occurrences

The number of times a specific value is captured, plus the number of page views for which the given value persisted. In other words, Occurrences are sum of page views and page events. Occurrences are available in Analysis Workspace and in Ad Hoc Analysis.

## Comparing Instances and Occurrences {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Two metrics that appear to be similar are listed:

**[Instances](/help/components/c-variables/c-metrics/metrics-instance.md)**: The number of times that a value was set for a variable.

**Occurrences**: The total number of times a value was set or persisted. 

|  Situation  | Description  |
|---|---|
|  Occurrences higher than Instances  | This is to be expected for conversion variables, as occurrences also includes the number of times the variable was defined (instances).  |
|  Instances higher than Occurrences  | This is not possible in reporting, as all instances are recorded as occurrences as well.  |
|  Instances equal to Occurrences  | This is most common for traffic variables, as by nature they do not persist beyond the image request.  |

>[!MORE_LIKE_THIS]
>
>* [Instances](/help/components/c-variables/c-metrics/metrics-instance.md)
