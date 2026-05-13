---
title: Copy processing rules
description: Learn how to copy processing rules from one report suite to another.
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
TQID: https://experienceleague.adobe.com/oTt61LKoudFaDmgFqCXE3K3t-ni-Twjh5tHaHM4ATg0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Copy processing rules between report suites

Copying processing rules saves you from manually recreating the same logic in multiple report suites. You can use the copy feature to share processing rules functionality across many report suites easily, or to copy tested functionality from a development report suite to a production report suite.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL Copy processing rules]**

This interface allows two options:

* **Replace all processing rules**: This option deletes all processing rules from the destination report suite, then adds all processing rules to the destination report suite in the same order. You cannot select a limited number of processing rules to replace.
* **Append specific processing rules**: This option allows you to select one or more processing rules. Appended rules are added to the end of the processing rules list in each destination report suite. Consider processing rule order and rules that already exist when appending rules to each destination report suite.

When selecting processing rules to append or report suites to copy to, you can use `Ctrl`/`Cmd` + `Click` to select multiple processing rules or report suites. Once you select the desired report suites to copy to, select **[!UICONTROL Copy]** and confirm the modal window that appears.

>[!WARNING]
>
>Processing rules directly affect data collection, and can cause data loss if used incorrectly. Always test processing rules in a development report suite before copying them to a production report suite to mitigate data quality issues.
