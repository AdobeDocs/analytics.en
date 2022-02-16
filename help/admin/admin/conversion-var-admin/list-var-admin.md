---
title: List variables
description: Create and configure list variables for use in reporting.
feature: Admin Tools
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
---
# List variables

Create and configure list variables for use in reporting. Set their delimiter, expiration, allocation, and max values here.

You can access the configuration in the Admin Console:

1. Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**
2. Select the report suite.
3. Click  **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

* **Name**: Each delimited value can contain a maximum of 255 characters (or less if using multi-byte characters). This is the maximum length of each element.
* **Value Delimiter**: The character used to separate values within the List Var. Most commonly these are characters such as commas, colons, pipes, or something similar.

  >[!NOTE]
  >
  >Multi-byte characters are not supported as delimiters in List Vars. The delimiter must be single byte.

* **Expiration**: Similar to eVar expiration, this determines the amount of time that can occur between the List Var and the conversion event for them to be related.
  * **At a page view or visit level**: Success events beyond the page view or visit would not link back to any values within the List Var.
  * **Based on a time period, such as day, week, month, etc**: Success events beyond the specified time period would not link back to any values within the List Var. A custom number of days can be defined as well.
  * **Specific conversion events**: Any other success events that fire after the specific event designated would not link back to any values within the List Var.
  * **Never**: Any amount of time can pass between the List Var and success event.

* **Allocation**: This setting determines how success events divide credit between values:
  * **Full**: All variable values defined prior to the variable's expiration get full credit for success events.
  * **Linear**: All variable values defined prior to the variable's expiration get credit divided credit for conversion events.
  * Variable values are never overwritten, but instead added to the values that get credit for success events.

* **Max Values**: Designates the number of active values allowed for this list variable. For example, if set to 3, only the last 3 values captured is saved and any previous values captured are discarded. Note that if multiple values for the same list var are sent in on the same hit and you have restricted using max values, each value will have the same timestamp and there is not guarantee as to which value is saved.

A limit of 250 maximum values are stored at one time per visitor. If 250 values per visitor are exceeded, the latest 250 values are used. Expiration for these values is based on the configured expiration for the variable.

The Max Values setting is useful to limit attribution to a specific number of values. For example, if a list var is set to "A,B,C" on the first page of a visit, then set to "X,Y,Z" on the next page, attribution is distributed to these six values based on the allocation. If you wanted to limit attribution to only "X,Y,Z", you can set max values to three.
