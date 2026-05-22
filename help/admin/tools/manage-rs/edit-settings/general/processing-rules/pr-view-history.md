---
title: Processing rules view history
description: View what changes have been previously made to processing rules.
feature: Processing Rules
role: Admin
exl-id: c1d4eb01-0888-483a-9a65-83a64e818f88
TQID: 'https://experienceleague.adobe.com/LNxzPDICHbau1f5wqYR5QTBfh9Vuvgo8JkqJ1XFnl7M'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Processing rules view history

This interface lets you see all changes that have ever been made to processing rules for this report suite. It is valuable in cases where you might need to revert changes, or troubleshoot issues that impact data quality.

Every time changes are saved to processing rules, a "snapshot" is created that keeps a record of the state of processing rules at that point.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL View history]**

The table displays three columns:

* **[!UICONTROL Created]**: The timestamp when the snapshot was created.
* **[!UICONTROL User]**: The user that made changes to processing rules.
* **[!UICONTROL View]**: A link that takes you to what the processing rules were at that time.

Select the **[!UICONTROL Copy to current ruleset]** button when viewing your rule history to revert processing rules to the selected date. Reversions are not applied until after you select **[!UICONTROL Save]**.
