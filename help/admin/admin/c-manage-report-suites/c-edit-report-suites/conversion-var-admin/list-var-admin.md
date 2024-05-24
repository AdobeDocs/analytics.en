---
title: List variables
description: Create and configure list variables for use in reporting.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
---
# List variables

Create and configure list variables for use in reporting. Set their delimiter, expiration, allocation, and max values. Collect data for list variables using [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]**

* **[!UICONTROL Name]**: The name of the list variable. This name is the dimension label in Analysis Workspace.

* **[!UICONTROL Status]**: Enable or disable collecting data for this variable. If a variable is disabled, no data is collected, even if your implementation sends data to that variable.

* **[!UICONTROL Value Delimiter]**: The character used to separate values within the list variable. Most commonly these are characters such as commas, colons, pipes, or something similar. Multi-byte characters are not supported as delimiters in list variables.

* **[!UICONTROL Expire After]**: Similar to eVar expiration, this field determines the amount of time that can occur between the list variable and the conversion event for them to be related.
  * **At a page view or visit level**: Success events beyond the page view or visit would not link back to any values within the list variable.
  * **Based on a time period, such as day, week, month, etc**: Success events beyond the specified time period would not link back to any values within the list variable. A custom number of days can be defined as well.
  * **Specific conversion events**: Any other success events that fire after the specific event designated would not link back to any values within the list variable.
  * **Never**: Any amount of time can pass between the list variable and success event.

* **[!UICONTROL Allocation]**: This setting determines how success events divide credit between values:
  * **Full**: All variable values defined prior to the variable's expiration get full credit for success events.
  * **Linear**: All variable values defined prior to the variable's expiration get credit divided credit for conversion events.
  * Variable values are never overwritten, but instead added to the values that get credit for success events.

* **[!UICONTROL Description]**: A description of how your organization uses the list variable.

* **[!UICONTROL Max Values]**: Designates the number of active values allowed for this list variable. For example, if set to 3, only the last 3 values captured is saved and any previous values captured are discarded. Note that if multiple values for the same list variable are sent in on the same hit and you have restricted using max values, each value will have the same timestamp and there is not guaranteed as to which value is saved. If a visitor persists more values than the max allowed, the most recent values are used. Up to 250 max values are allowed.

  This setting is useful to limit attribution to a specific number of values. For example, if a list variable is set to `"A,B,C"` on the first page of a visit, then set to `"X,Y,Z"` on the next page, attribution is distributed to these six values based on its allocation. If you wanted to limit attribution to only `"X,Y,Z"`, you can set max values to three.
