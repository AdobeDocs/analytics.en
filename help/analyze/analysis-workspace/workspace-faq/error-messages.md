---
description: List of error messages in Adobe Analysis Workspace and its related components
title: Common error messages in Analysis Workspace
feature: Workspace Basics
role: Business Practitioner, Administrator
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
---
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL The request is too complex.] |Your reporting request is too large and cannot be executed. Contributors to this error are timeouts due to the request's size, too many matched items in a segment or search filter, too many metrics included, incompatible dimension and metric combinations, etc. | Simplify your request by removing some columns or rows in your table, or consider splitting the table into separate requests. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension you are using. | Replace the dimension in your table with one that is compatible with [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
