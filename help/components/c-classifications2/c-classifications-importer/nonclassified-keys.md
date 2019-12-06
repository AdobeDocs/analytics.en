---
description: Non-classified keys are grouped together in classification reports as a single line item labeled None. It can be useful to rename None to something more descriptive.
subtopic: Classifications
title: Non-classified keys
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
---

# Non-classified keys

Non-classified keys are grouped together in classification reports as a single line item labeled None. It can be useful to rename None to something more descriptive.

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Non-classified keys are grouped together in classification reports as a single line item labeled *`None`*. It can be useful to rename *`None`* to something more descriptive.

For example, suppose your tracking codes contain information that delineates the type of mobile campaign the tracking code is associated with. You are using classification (Mobile Campaign Type) to group these tracking codes into categories such as Mobile Web, iOS Application, Android Application, and so on. Some campaigns might not be mobile campaigns and are therefore not classified with a mobile campaign type. All non-classified tracking codes would be grouped under *`None`* in the [!UICONTROL Mobile Campaign Type] report.

## Rename the None classification key {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. Using the importer, export classifications to a local file.
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. In the row you added, type the more descriptive name in the appropriate classification column(s).

   To follow the example in this documentation, you might type "non-mobile campaign" in a column named [!UICONTROL Mobile Campaign Name].

   This entry renames *`None`* to *`non-mobile campaign`* in the [!UICONTROL Mobile Campaign Type] report.
1. [Import the data](/help/components/c-classifications2/c-classifications-importer/import-file.md) back into the system.
