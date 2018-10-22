---
description: You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.
seo-description: You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.
seo-title: Create a field viewer
solution: Analytics
title: Create a field viewer
topic: Data workbench
uuid: e96763e4-2cda-45d9-b226-aa1b76ed7f5d
index: y
internal: n
snippet: y
---

# Create a field viewer

You can open a field viewer as a callout from a dependency map or as a standalone visualization from the Admin menu.

## Create a field viewer from a dependency map {#section_040CB83C902B49C48B841D35ABC127E5}

When you open a field viewer from a dependency map (as shown in [Opening Field Viewers](../../../c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept_0F0738AC50804A33818487222C337C27)), the viewer is populated automatically based on the log source, transformation, or dimension that you right-click. For a log source or a transformation, the fields in the viewer are inputs or outputs of the log source or transformation. For a dimension, the fields are inputs of the dimension. You can add and remove fields as desired.

## Create a field viewers as a standalone visualization {#section_11D10E46631D4FDCA45D7534336E1E80}

When you open a field viewer as a standalone visualization, you can create a [!UICONTROL Log Processing Field Viewer] or a [!UICONTROL Transformation Field Viewer]. The viewer is blank, and you must add the desired fields to the viewer. For a [!UICONTROL Log Processing Field Viewer], you can add fields from the [!DNL Log Processing.cfg] file or any [!UICONTROL Log Processing dataset include] file. For a [!UICONTROL Transformation Field Viewer], you can add fields from the [!DNL Transformation.cfg] file or any [!UICONTROL Transformation dataset include] file.

For more information about configuration and include files, see the *Dataset Configuration Guide*.

## Add and remove a field {#section_9C0D4F5735A044A8B21DC7A99C63A59A}

**To add a field to a field viewer**

* Right-click within the field viewer and click **[!UICONTROL Fields]** > *< **[!UICONTROL field name]**>* > *< **[!UICONTROL instance]**>*.

  -or- 

* Right-click within an existing column in the field viewer and click **[!UICONTROL Fields]** > *< **[!UICONTROL field name]**>* > *< **[!UICONTROL instance]**>*.

Field name refers to the field’s name, and instance refers to where in the dataset configuration the field is used, such as a dataset processing stage or a transformation. Some fields are used in multiple places within the dataset configuration (for example, a field can be modified by multiple transformations), so you must select which instance of the field to add to your field viewer.

In the list of available fields, an X appears to the left of any field already displayed in the viewer.

**To remove a field from a field viewer**

* Right-click within the column for the field that you want to remove and click **[!UICONTROL Remove Field]**.

