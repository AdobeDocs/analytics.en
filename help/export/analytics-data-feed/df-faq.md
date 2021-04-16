---
description: Frequently asked questions around data feeds
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Data feeds FAQ
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
---
# Data feeds FAQ

Frequently asked questions around data feeds.

## What is the difference between columns with a `post_` prefix and columns without a `post_` prefix?

Columns without the `post_` prefix contains data exactly as it was sent to data collection. Columns with a `post_` prefix contains the value after processing. Examples that can change a value are variable persistence, processing rules, VISTA rules, currency conversion, or other server-side logic Adobe applies. Adobe recommends using the `post_` version of a column where possible.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## How do data feeds handle case sensitivity?

In Adobe Analytics, most variables are considered as case-insensitive for reporting purposes. For example, 'snow', 'Snow', 'SNOW', and 'sNow' are all considered the same value. Case sensitivity is preserved in data feeds.

If you see different case variations of the same value between non-post and post columns (for example, 'snow' in the pre column, and 'Snow' in the post column), your implementation uses both uppercase and lowercase values across your site. The case variation in the post column was previously passed in and is stored in the virtual cookie, or was processed around the same time for that report suite.

## Are bots filtered by Admin console bot rules included in data feeds?

Data feeds do not include bots filtered by [Admin console bot rules](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Why do I see multiple `000` values in the `event_list` or `post_event_list` data feed column?

Some spreadsheet editors, especially Microsoft Excel, automatically round very large numbers. The `event_list` column contains many comma-delimited numbers, sometimes causing Excel to treat it as a large number. It rounds the last several digits to `000`.

Adobe recommends against automatically opening `hit_data.tsv` files in Microsoft Excel. Instead, use Excel's Import Data dialog box and make sure that all fields are treated as text.

## Why can't I extract "Hourly" files from data that is more than 7 days old?

For data that is more than 7 days old, a day's "Hourly" files are combined into a single "Daily" file. 

Example: A new Data Feed is created on March 9, 2021, and the data from January 1, 2021 to March 9 is delivered as "Hourly". However, the "Hourly" files prior to March 2, 2021 are combined into a single "Daily" file. You can extract "Hourly" files only from data that is less than 7 days old from the creation date. In this case, from March 2 to the March 9.
