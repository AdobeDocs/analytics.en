---
title: Create a Classification Set
description: Available fields and descriptions when creating a Classification Set.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
---
# Create a Classification Set

You can use the Classification Set Manager to create a Classification Set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a Classification Set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the Classification Set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification. Primary classifications are typically used; Lookup classifications represent [Sub-classifications](../c-sub-classifications.md).
* **[!UICONTROL Subscriptions]** The Report Suite and dimension that this Classification Set applies to. Support for multiple Report Suites is planned.

If a Classification Set exists for a given Report Suite + variable, the Classification is added to the schema instead.
