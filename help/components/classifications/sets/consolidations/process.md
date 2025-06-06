---
title: Classification set consolidation process
description: The full process of consolidating classification sets.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
---
# Classification set consolidation process

Classification consolidations allow you to take classifications from multiple datasets and combine them into one. Use this interface to create a classification set consolidation from start to finish. This interface is most valuable to organizations moving from a legacy classification architecture towards a classification set architecture. Most organizations that are already on the classification set architecture typically do not need to use this consolidation workflow.

## Creation

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

## Validation

Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

## Run

Once a consolidation is validated, you can run it. Running a consolidation provides a similarity report with the following table columns:

* **[!UICONTROL Dataset name]**: The name of the classification set.
* **[!UICONTROL Mismatch]**: The percent of rows where key values did not match the source classification set. If the mismatch percent is high, it is possible that the classification data is too different. Check and make sure that the selected classification sets have similar classification data.
* **[!UICONTROL Absent]**: The percent of rows where key values were in that classification set but not in the source classification set. All absent rows are added to the consolidated classification set.

## Approve

The last call before removing individual classification sets and replacing them with a consolidated classification set. Validate that everything is correct, then select **[!UICONTROL Approve]**.

Once approved, the consolidated classification set is created. The status is set to [!UICONTROL Complete], and no further action is required for the consolidation.
