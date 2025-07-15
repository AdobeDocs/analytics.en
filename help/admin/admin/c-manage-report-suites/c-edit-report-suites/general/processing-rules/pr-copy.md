---
title: Copy processing rules
description: Learn how to copy processing rules from one report suite to another.
feature: Processing Rules
role: Admin
---
# Copy processing rules between report suites

Copying processing rules saves you from manually recreating the same logic in multiple report suites. You can use the copy feature to easily share processing rules functionality across many report suites, or to copy tested functionality from a development report suite to a production report suite.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL Copy processing rules]**

This interface allows two options:

* **Replace all processing rules**: This option deletes all processing rules from the destination report suite, then adds all processing rules to the destination report suite in the same order. You cannot select a limited number of processing rules to replace.
* **Append specific processing rules**: This option allows you to select one or more processing rules. Appended rules are added to the end of the processing rules list in each destination report suite. Consider processing rule order and rules that already exist when appending rules to each destination report suite.

When selecting processing rules to append or report suites to copy to, you can use `Ctrl`/`Cmd` + `Click` to select multiple processing rules or report suites. Once you select the desired report suites to copy to, select **[!UICONTROL Copy]** and confirm the modal window that appears.

>[!WARNING]
>
>Processing rules directly affect data collection, and can cause data loss if used incorrectly. Always test processing rules in a development report suite before copying them to a production report suite to mitigate data quality issues.
