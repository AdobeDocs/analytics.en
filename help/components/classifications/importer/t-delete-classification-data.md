---
description: Steps that describe how to delete or remove classification data.
title: Delete classification data
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
---
# Delete classification data

Sometimes it is necessary to remove classification data after it is uploaded. Use either `~empty~` or `~deletekey~`, depending on what you want to remove.

## Steps to remove classification data

Removing classification data involves uploading a classification file containing `~empty~` or `~deletekey~` in the appropriate cells.

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Select the report suite and data set you would like to remove classification data from.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values with either `~empty~` or `~deletekey~`.
1. Save the file as a tab-delimited text file.
1. Click **[!UICONTROL Import File]**, and upload the saved classification file back into Adobe Analytics.

## Deleting an individual classification value

Multiple classifications can belong to the same variable. For example, you can have 2 different classifications of eVar1. If you would like to only remove a single classified value, replace the classification value with `~empty~`. For example:

| Inventory SKU (eVar8) | Inventory Name | Inventory Category |
| --- | --- | --- |
| 857467 | V-neck sweater | Women's clothing |
| 948203 | Ankle bracelet | Jewelry |
| 174391 | White corduroy pants | `~empty~` |

Using `~empty~` under the Inventory Category classification still preserves data for the Inventory Name classification. The `~empty~` value only deletes classification data for that cell.

## Deleting an entire classification row

Use `~deletekey~` in any column to delete the entire classification row. For example:

| Inventory SKU (eVar8) | Inventory Name | Inventory Category |
| --- | --- | --- |
| 857467 | V-neck sweater | Women's clothing |
| 948203 | Ankle bracelet | Jewelry |
| 174391 | White corduroy pants | `~deletekey~` |

Using `~deletekey~` under the Inventory Category classification deletes all classification data for the key value `174391`. It becomes as if the row was never classified.

## Pitfalls and tips

* If using `~deletekey~`, you only need one per row in a classification file.
* `~empty~` and `~deletekey~` must be *exact* matches. No spaces or capitalization are allowed.
* You cannot delete values within the key column, These values are passed directly into the variable and is permanent.
* If you are removing a classification value that has subclassifications, those subclassifications are also removed. Classifications cannot exist without a key value, and a subclassification's parent is its key value.
* It is possible to remove subclassification data while leaving its parent classification intact.
