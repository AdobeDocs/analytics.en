---
title: Classification Set Rules
description: Understand how to view and edit rules for a classification set.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
---
# Classification set rules

>[!IMPORTANT]
>
>Classification sets do not yet support rules. Rules functionality will be added to the classification sets interface before the legacy rule builder functionality becomes unavailable.
>If you do require rules for classifications, continue to use the [Classifications rule builder](/help/components/classifications/crb/classification-rule-builder.md).

<!--
Classification set rules allow you to automatically classify values based on the value that the variable is set to. These rules apply to all incoming variable values for all subscriptions of the classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired classification set name > **[!UICONTROL Rules]**

![classification set rules UI](../../assets/csets-rules.png)

## Rule settings

Settings that apply to the entire set of rules.

* **[!UICONTROL Rules overwrite]**: Determines the behavior of all rules in cases where a classification value exists.
  * **[!UICONTROL Apply to all values]**: If a rule matches, always overwrite the classification value.
  * **[!UICONTROL Apply only to unset values]**: If a rule matches, only write the classification value if it is blank. If a classification value exists, do nothing.
* **[!UICONTROL Lookback window]**: When this rule is activated, all rules run against all unique values seen within the lookback window set here.
   * If you access the **[!UICONTROL Rules]** interface for the first time for a classification set, or decided so far to continue to use the legacy rules builder interface, you are presented with a dialog that allows you to select how to get started. 

     ![Rules migration](assets/rules-migration.png)
  
     The options are:

## Rules

A list of rules that run for each unique value.

* **[!UICONTROL Search]**: A search box that allows you to filter rules by match criteria.
* **[!UICONTROL Add rule]**: Adds a blank row to the rule table.
* **[!UICONTROL Test rule set]**: Brings up a test UI that allows you to validate your rules. On the left, you can manually type key values, or you can drag and drop a classification file to import many values to test against. On the right is a table that shows preliminary results of what classified values would look like if the rule set was activated. Since this interface is only for validation, no values are classified.

Select one or more rules by clicking the checkbox next to the desired rule. Selecting a rule reveals the following options:

* **[!UICONTROL Delete]**: Deletes the row from the rule table.
* **[!UICONTROL Duplicate]**: Copies the selected rows to new rows in the rule table.

## Rule table

The rule table is separated vertically into two main parts: matching condition and classification action. Each row (an individual rule) contains a matching condition and a classification action.


-->