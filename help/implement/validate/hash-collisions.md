---
title: Hash collisions
description: Describes what a hash collision is and how it can manifest.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
---
# Hash collisions

Dimensions in Adobe Analytics collect string values. Sometimes these strings are hundreds of characters long, while other times they are short. To improve performance, these string values are not used directly in processing. Instead, a hash is computed for each value to make all values a uniform size. All reports run on these hashed values, which drastically increase their performance.

For most fields, the string is first converted to all lowercase. Lowercase conversion reduces the number of unique values. Values are hashed on a monthly basis - the case for a given value uses the first value seen each month. From month to month, there is a small possibility that two unique variable values hash to the same value. This concept is known as a *hash collision*.

Hash collisions can manifest in reports as follows:

* If you view a report over time and see an unexpected spike, it is possible that multiple unique values for that variable use the same hash.
* If you use a segment and see an unexpected value, it is possible that the unexpected dimension item uses the same hash as another dimension item that matched your segment.

## Odds of a hash collision

Adobe Analytics uses 32-bit hashes for most dimensions, which means that there are 2<sup>32</sup> possible hash combinations (approximately 4.3 billion). A new hash table for each dimension is created each month. The approximate odds of encountering a hash collision based on the number of unique values are as follows. These odds are based on a single dimension for a single month.

| Unique values | Odds |
| --- | --- |
| 1,000 | 0.01% |
| 10,000 | 1% |
| 50,000 | 26% |
| 100,000 | 71% |

{style="table-layout:auto"}

Similar to the [birthday paradox](https://en.wikipedia.org/wiki/Birthday_problem), the likelihood of hash collisions drastically increases as the number of unique values increases. At 1 million unique values, it is likely that there are at least 100 hash collisions for that dimension.

## Mitigating hash collisions

Most hash collisions happen with two uncommon values, which have no meaningful impact on reports. Even if a hash collides with a common and uncommon value, the result is negligible. However, in rare cases where two popular values experience a hash collision, it is possible to see its effect clearly. Adobe recommends the following to reduce its effect in reports:

* **Change the date range**: Hash tables change each month. Changing the date range to span another month can give each value different hashes that don't collide.
* **Reduce the number of unique values**: You can adjust your implementation or use [Processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) to help reduce the number of unique values that a dimension collects. For example, if your dimension collects a URL, you can strip query strings or protocol.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
