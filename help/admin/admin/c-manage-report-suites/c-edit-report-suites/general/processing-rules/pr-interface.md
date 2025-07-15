---
title: Processing rules interface
description: Navigate the interface to create, edit, or delete processing rules.
feature: Processing Rules
role: Admin
---
# Processing rules interface

The processing rules interface allows you to create, edit, or delete processing rules.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Processing rules directly affect data collection, and can cause data loss if used incorrectly. Always test processing rules in a development report suite before enabling them in a production report suite to mitigate data quality issues.

## Overarching structure

This interface contains two main components:

* **[!UICONTROL Processing order]**: Rules run exactly in the order that you have specified, starting at rule 1. Every hit runs through every rule; there are no early-out conditions. Make sure that the conditions of every processing rule accommodate every hit sent to the report suite.
* **[!UICONTROL Rule sets]**: The definitions of each of your processing rules.

You can have up to 150 processing rules and up to 30 conditions per processing rule. There is not a reasonable limit to the number of actions per processing rule.

## Rule set structure

Each processing rule contains the following sections:

* **Rule title**: The label of the rule. It does not impact processing rule logic, but is valuable to help keep track of what the rule does.
* **Condition**: Shown as the text, "[!UICONTROL If any/all of the following are true]". If you do not include a condition, the rule always runs on every hit.
* **Action**: If no condition exists, the text is shown as, "[!UICONTROL Always execute]". If a condition exists, the text is shown as, "[!UICONTROL Then do the following]". If the above condition evaluates to `true`, every action listed in this section potentially executes. In addition to a rule's condition, you can _also_ attach conditions to individual actions. The following actions are available:
  * **[!UICONTROL Overwrite value of]**: Overwrites the desired variable with either another variable, a static value, or a concatenated value.
  * **[!UICONTROL Delete value of]**: Deletes the desired variable value for that hit.
  * **[!UICONTROL Set event]**: Triggers the desired event. Typically you would set events to a custom value of `1`; setting events to values other than `1` or even setting them to values set in context data variables is also allowed.
* **Otherwise action**: If a condition exists, this section appears as, "[!UICONTROL Otherwise do the following]". If the above condition evaluates to `false`, every action listed in this section potentially executes. This section follows the same rule actions as above, including the ability to overwrite values, delete values, and set events.
* **Reason**: Record who requested the rule and what it depends on. It does not impact processing rule logic, but is valuable to help keep track of why the rule exists.

See [Dimensions and metrics available to processing rules](pr-variables.md) for a comprehensive list of variables that you can use in this interface.

* Any variable that allows "Read" can be used in a condition.
* Any variable that allows "Write" can be used in an action.
