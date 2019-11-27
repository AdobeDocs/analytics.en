---
description: Frequently asked questions around data feeds
keywords: Data Feed;job;pre column;post column;case sensitivity
solution: Analytics
title: Data feeds FAQ
---

# Data feeds FAQ

Frequently asked questions around data feeds.

## What is the difference between columns with a `post_` prefix and columns without a `post_` prefix?

Columns without the `post_` prefix contains data exactly as it was sent to data collection. Columns with a `post_` prefix contains the value after processing. Examples that can change a value are variable persistence, processing rules, VISTA rules, currency conversion, or other server-side logic Adobe applies. Adobe recommends using the `post_` version of a column where possible.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## How do data feeds handle case sensitivity?

In Adobe Analytics, most variables are considered as case-insensitive for reporting purposes. For example, 'snow', 'Snow', 'SNOW', and 'sNow' are all considered the same value. Case sensitivity is preserved in data feeds.

If you see different case variations of the same value between non-post and post columns (for example, 'snow' in the pre column, and 'Snow' in the post column), your implementation uses both uppercase and lowercase values across your site. The case variation in the post column was previously passed in and is stored in the virtual cookie, or was processed around the same time for that report suite.