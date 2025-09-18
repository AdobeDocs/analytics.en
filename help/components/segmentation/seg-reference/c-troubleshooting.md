---
description: Understand how to troubleshoot and fix issues related to segments.
title: Troubleshooting
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
---
# Troubleshooting

This article lists some common issues with segments and how to troubleshoot these issues.

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## Why does my segment return no data at all? {#no-data}

Possible reasons:

* Reverse nesting - for example, nesting a ![User](/help/assets/icons/User.svg) **[!UICONTROL Visitor]** container under a ![Visit](/help/assets/icons/Visit.svg) **[!UICONTROL Visit]** container.
* The report does not support segmentation.
* There is no data matching the segmentation criteria.

## Why can't I see the segment I created in the Segment manager? {#invisible}

Possible reasons:

* Some dimensions are available only in Data Warehouse and not in the Segment manager.
* Segment is checked only for a specific report suite.
* A shared segment might have been deleted by another user.
* Segments could not loaded due to a data center or browser cache issue.
* The segment has not been saved.
* IP address may be blocked at the user's end.

## Why does the data shown after applying a segment seem incorrect? {#page-data}

Possible reasons:

* Rules or operators are incorrect for the required result.
* Incorrect use of containers in the segment.
* Traffic variables used to segment are not set properly or are expired.
