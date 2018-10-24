---
description: The pre column contains the data as it was sent to data collection. The post column contains the value after processing.
keywords: Data Feed;job;pre column;post column;case sensitivity
seo-description: The pre column contains the data as it was sent to data collection. The post column contains the value after processing.
seo-title: Pre and post columns
solution: Analytics
title: Pre and post columns
topic: Reports and analytics
uuid: 8041ce9a-ce27-4cff-bb7d-496da5ebe534
index: y
internal: n
snippet: y
---

# Pre and post columns

The pre column contains the data as it was sent to data collection. The post column contains the value after processing.

For example, variable persistence, processing rules, VISTA rules, and currency conversion might change the final value recorded for a variable that appears in the post column. For most calculations you want to use the post column unless you are applying custom business logic (for example, applying a custom formula to determine attribution).

If a column does not contain a pre or a post version (for example, `visit_num`), then the column can be considered a post column. Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## Case Sensitivity in Values {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

Most Analytics variables are considered as case-insensitive for reporting purposes, meaning different case variations are considered to be the same value ("snow", "Snow", "SNOW", and "sNow" are all considered to be the same value). However, for display purposes, case sensitivity is preserved since most customers prefer to be able to send in mixed case characters to display in reports.

When processing the data feed, you can lowercase values for comparison purposes, though you'll likely want to preserve case for display purposes.

If you see different case variations of the same value between the pre and post columns (for example, "snow" in the pre column, and "Snow" in the post column), it indicates that you are passing in both uppercase and lowercase versions of the same value across your site. The case variation in the post column was previously passed in and is stored in the virtual cookie, or was processed around the same time for that report suite. For example:

Hit 1: s.list1="Tabby,Persian,Siamese”;

Hit 2: s.list1=“tabby,persian,siamese”;

When hit 2 is reported in the data feed, the pre column will contain the exact casing passed in (tabby,persian,siamese), but the value from hit 1 is likely persisted for that visit and will be reported in the post column (which will be Tabby,Persian,Siamese) since hit 1 and 2 contain the exact same value when a case-insensitive comparison is performed. 
