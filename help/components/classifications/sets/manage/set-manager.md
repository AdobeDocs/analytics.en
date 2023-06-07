---
title: Classification set manager
description: Manage classification sets in Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
---
# Classification set manager

The Classification set manager allows you to create, edit or delete classification sets.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Classification sets consist of **Subscriptions** (report suite and dimension combinations) and **Classification names** (The additional dimensions containing classification data).

## Filter classification sets

The left side of the Classification set manager provides filter settings to locate the desired classification set. Clicking the filter icon toggles the filter settings visibility. You can filter classification sets by **[!UICONTROL Tags]**, **[!UICONTROL Report suite]**, or **[!UICONTROL Owner]**.

![Classification set filters](../assets/classification-set-filters.png)

## Classification set manager columns

The following columns are available in the Classification set manager:

* **[!UICONTROL Classification set]**: The classification set name. Click a classification set name to [edit its settings](settings.md).
* **[!UICONTROL Subscriptions]**: The number of subscriptions that this classification set applies to.
* **[!UICONTROL Owner]**: The owner of the classification set.
* **[!UICONTROL Classifications]**: The number of classification dimensions that the classification set contains.
* **[!UICONTROL Automated]**: Determines if the classification set is configured to automatically import data from a cloud location. Automation can be configured in the classification set's [schema](schema.md).
* **[!UICONTROL Last Modified]**: The date and time that the classification set was last modified.

## Create or edit options

The following buttons are available in the Classification set Manager:

* **[!UICONTROL Add]**: [Create](create.md) a classification set.
* **[!UICONTROL Search by title]**: Search for classification sets by name.
* **[!UICONTROL Load more]**: The Classification set Manager initially displays up to 1000 classification sets. Click this button to load 1000 more classification sets.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Classification set].

Select one or more classification sets by clicking the checkbox next to the desired classification set. Selecting a classification set reveals the following options:

* **[!UICONTROL Tag]**: Add one or more tags to the selected classification set(s), which allows you to organize or group classification sets to make them easier to locate in the future.
* **[!UICONTROL Delete]**: Deletes the classification set. Classification dimensions based on this classification set are no longer available. Scheduled projects using the deleted classification set continue using dependent dimensions until you re-save the scheduled project.
* **[!UICONTROL Consolidate]**: Start a new [consolidation](../consolidations.md).
* **[!UICONTROL Rename]**: Rename the selected classification set.
