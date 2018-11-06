---
description: Steps that describe how to delete or remove classification data.
seo-description: Steps that describe how to delete or remove classification data.
seo-title: Delete classification data
solution: Analytics
subtopic: Classifications
title: Delete classification data
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
index: y
internal: n
snippet: y
---

# Delete classification data

Steps that describe how to delete or remove classification data.

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. Select the report suite and data set you would like to remove classification data from.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. This command treats the classification as if it never occurred for the specified key. It completely removes it and any column data from the lookup tables.

   **Caveat**: You only need one column containing [!DNL ~deletekey~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. This command removes all metadata from the row. Adobe interprets this as though the key was never classified, and displays it in the [None](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF) category. 

1. Save the file, and upload it using the [!UICONTROL Import File] tab.

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Properties of this Command**

* [!DNL ~empty~] must be lowercase without spaces. The following entries are invalid:

    * [!DNL ~EMPTY~] 
    * [!DNL ~ empty ~] 
    * [!DNL ~Empty~]

* You cannot delete values within the key column. This is data passed directly into reporting and is permanent. 
* If you are removing a classification value that has subclassifications, they are also removed. Classifications cannot exist without a key value, and a subclassification's parent is its key value. 
* It is possible to remove subclassification data while leaving its parent classification intact.

