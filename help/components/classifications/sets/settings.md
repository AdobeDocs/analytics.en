---
title: Classification Set settings
description: Create or edit a Classification Set.
---

# Classification Set settings

Configure a Classification Set, upload data, or download data.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Click the desired Classification Set name

When editing a Classification Set, two tabs are available; **[!UICONTROL Schema]** and **[!UICONTROL Settings]**.

## Settings

The following fields are available in the [!UICONTROL Settings] tab and can be edited:

* **[!UICONTROL Name]**: The Classification Set name.
* **[!UICONTROL Description]**: The description for the Classification Set.
* **[!UICONTROL Owner name]**: The owner name.
* **[!UICONTROL Owner email]**: The owner's email address.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email address that are notified of issues with this Classification Set.
* **[!UICONTROL Tags]**: Add one or more tags to the selected Classification Set(s), which allows you to organize or group Classification Sets to make them easier to locate in the future.

Additional fields are available for informational purposes, and cannot be edited:

* **[!UICONTROL Type]**: The type of classification between [!UICONTROL Primary] and [!UICONTROL Lookup]. Primary classifications are typically used.
* **[!UICONTROL Subscriptions]**: The Report Suite and variable that the Classification Set applies to. Only one Report Suite is currently supported for a given Classification Set; support for multiple Report Suites is planned.

## Schema

View currently configured classification dimensions for this subscription. The following buttons are available:

* **[!UICONTROL Upload]**: Manually upload classification data for one or more classification dimensions. JSON, CSV, TSV, and TAB files are supported. Uploading a valid file shows a table preview of data to classify.
  * **[!UICONTROL File encoding]**: Select the correct file encoding using this dropdown. Valid options include [!UICONTROL UTF-8] and [!UICONTROL Latin1].
  * **[!UICONTROL List delimiter]**: Select the correct list delimiter. If using a downloaded file or template file, make sure the that [!UICONTROL List delimiter] here matches the [!UICONTROL List delimiter] when the file was downloaded.
  * **[!UICONTROL Apply]**: Save the uploaded classification data to the Classification Set.
