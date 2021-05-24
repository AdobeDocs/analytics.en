---
description: The Segment Builder allows you to compare and constrain values using selected operators.
title: Comparison Operators for Segments
feature: Segmentation
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
---
# Comparison Operators for Segments

The Segment Builder lets you compare and constrain values using selected operators. There are three categories of operators: Standard, Data Warehouse, and Distinct Count.

The only supported wildcard character is the asterisk: &#42;. If you need to search for &#42;, you can escape it with a backslash.

**Example**: Suppose you have a page name called "My cool product". The segment rule "Page name matches My&#42;product" will match the above page name. However, the rule "Page name matches My\\&#42;product" matches only the page name "My&#42;Product".

## Standard operators

| Operator | The selected dimension, segment, or metric event... |
|--- |--- |
| equals | Returns items that match exactly for a numeric or string value. Note:  If using wildcard characters, use the "matches" operator. |
| does not equal | Returns all items that do not contain the exact match of the value entered.  Note:  If using wildcard characters, use the "does not match" operator. |
| equals any of | Returns items that match exactly for any value in the input field (up to 500 items). For example, entering "Search Results, Homepage" with this operator would match "Search Results" and "Homepage", and count as 2 items. The input field for this operator is comma-delimited. |
| does not equal any of | Identifies items that match exactly for any value in the input field (up to 500 items), and then only returns items without these values. For example, entering "Search Results, Homepage" with this operator would identify "Search Results" and "Homepage" and then exclude them from the returned items. This example would count as 2 items. The input field for this operator is comma-delimited. |
| contains | Returns items that compare to the substrings of the values entered. For example, if the rule for "Page" contains "Search", then it will match any page that has the substring "Search" in it, including "Search Results", "Search", and "Searching". The "contains" clause is not case sensitive in Adobe Analytics, but it is case sensitive in Customer Journey Analytics. |
| does not contain | Returns the inverse of the "contains" rule. Specifically, all items that match the entered value will be excluded from the entered values. For example, if the rule for "Page" does not contain "Search", then it will not match any page that has the substring "Search" in it, including "Search Results", "Search", and "Searching". These values will be excluded from the results. |
| contains all of | Returns items compared to the substrings, including multiple values joined together. For example, entering "Search Results" with this operator would match "Search Results" and "Results of Search", but not "Search" or "Results" independently. It would match Search AND Results found together. The input field for this operator is space-delimited (100 words). |
| does not contain all of | Identifies items compared to substrings—including multiple values joined together—and then only return items without these values. For example, entering "Search Results" with this operator would identify "Search Results" and "Results of Search" (but not "Search" or "Results" independently) and then exclude these items. The input field for this operator is space-delimited (100 words). |
| contains any of | Returns items compared to the substrings, including multiple values joined or independently identified. For example, entering "Search Results" with this operator would match "Search Results", "Results of Search", "Search", and "Results". It would match either "Search" OR "Results" found together or independently. The input field for this operator is space-delimited (100 words). |
| does not contain any of | Identifies items based on substrings and then returns values that do not contain these substrings. It can have multiple joined values or values independently identified. For example, entering "Search Results" would match "Search Results", "Results of Search", "Search", and "Results" where either "Search" or "Results" are found together or independently. It would then exclude items that contain these substrings. The input field for this operator is space-delimited (100 words). |
| starts with | Returns items that start with the character or strings of the value entered. |
| does not start with | Returns all items that do not start with the characters or strings of the values entered. This is the inverse of the "starts with" operator. |
| ends with | Returns items that end with the character or strings of the value entered. |
| does not end with | Returns all items that do not end with the characters or strings of the value entered. This is the inverse of the "ends with" operator. |
| matches | Returns items that match exactly based on a given numeric or string value. The "matches" clause is case sensitive in Adobe Analytics and in Customer Journey Analytics. **Note**: Use this operator when using wildcard (globbing) features. Examples of "globbing":<ul><li>`a*e` would match `ae`, `abcde`, `adobe`, and `a whole sentence`</li><li>`adob*` would match `adobe`, `adobe analytics`, and `adobo recipe`</li><li>`*dobe` would match `dobe`, `adobe`, and `cute little dobe`</li></ul>|
| does not match | Returns all items that do not contain the exact match of the value entered. Note:  Use this operator when using wildcard (globbing) features. |
| exists | Returns the number of items that exist. For example, if you evaluate the Pages Not Found dimension using the "exist" operator, the number of error pages that exist is returned. |
| does not exist | Returns all items that do not exist. For example, if you evaluate the Pages Not Found dimension using the " does not exist" operator, the number of pages where this error page did not exist is returned. |

## Data Warehouse operators

| Operator | The selected dimension, segment, or metric event... |
| --- | --- |
| is less than | Returns items whose numeric count is less than the value entered. |
| is less than or equal to | Returns items whose numeric count is less than or equal to the value entered. |
| is greater than | Returns items whose numeric count is greater than the value entered. |
| is greater than or equal to | Returns items whose numeric count is greater than or equal to the value entered. |

## Distinct Count operators

You can segment on a distinct count of items within a dimension. Examples: "Visitors who viewed more than 5 distinct products," or "Visits where more than 5 distinct pages were seen."

| Operator | The selected dimension, segment, or metric event... |
| --- | --- |
| equals| Returns dimension items whose unique count equals the value entered. |
| does not equal |Returns dimension items whose unique count does not equal the value entered. |
| is greater than |Returns dimension items whose unique count is greater than the value entered. |
| is less than |Returns dimension items whose unique count is less than the value entered. |
| is greater than or equal to |Returns dimension items whose unique count is greater than or equal to the value entered. |
| is less than or equal to |Returns dimension items whose unique count is less than or equal to the value entered. |
