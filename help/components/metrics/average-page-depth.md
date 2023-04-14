---
title: Average page depth
description: How many pages in on average the dimension exists at.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
---
# Average page depth

The 'Average page depth' metric shows how far a dimension item extends into a given visit, on average. For example, your Home page (which is a dimension item for the Page dimension) typically shows a smaller average page depth than your Purchase Confirmation page, which likely extends further into a visit. You can use this information to optimize certain pages toward fresh visitors if the page has a low depth, on average.

>[!TIP]
>
>Use this metric alongside another metric, such as [Visits](visits.md), to obtain better insights. If you use this metric by itself, you might get dimension items containing anomalous page depths, which is typically not a valuable insight.

## How this metric is calculated

The first page of a visit has a page depth of `0`. The next page has a page depth of 1, and increases each page view until the end of the visit. This metric increases only with page view ([`t()`](/help/implement/vars/functions/t-method.md)) calls, and not with link tracking ([`tl()`](/help/implement/vars/functions/tl-method.md)) calls.

For a given dimension item, add all page depths for that dimension item, and divide it by visits. The resulting number is the average page depth, rounded to the nearest integer. Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

For example, consider the following example visit:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>If you want to see average page depth with a decimal place, create a calculated metric using this metric as the only element within the formula. Increase the decimal places in the calculated metric to the desired decimal.

## Percentages above 100%

This metric frequently contains percentages above 100%. The denominator is the entire dimension's average page depth, and the numerator is the dimension item's average page depth. 

If the entire dimension's average page depth is lower than a given dimension item's average page depth, you see percentages above 100%. Sorting ranked reports by this metric shows anomaly average page depth values, which is typically not valuable. Adobe recommends sorting by another metric, such as [Visits](visits.md), in ranked reports.
