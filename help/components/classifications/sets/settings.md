---
title: Classification Set settings
description: Create or edit a Classification Set.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
---
# Classification Set settings

Configure a Classification Set, upload data, or download data.

>[!NOTE]
>
>This feature is currently in limited release. If you would like access to this feature, contact Adobe Customer Care or your Account Manager, who can forward your request to the Classifications team for provisioning.

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
* **[!UICONTROL Subscriptions]**: The Report Suite and variable that the Classification Set applies to. Only one Report Suite is supported for a given Classification Set at this time; support for multiple Report Suites is planned.

## Schema

View currently configured classification dimensions for this subscription. The following buttons are available:

* **[!UICONTROL Upload]**: Manually upload classification data for one or more classification dimensions. JSON, CSV, TSV, and TAB files are supported. Uploading a valid file shows a table preview of data to classify.
  * **[!UICONTROL File encoding]**: Select the correct file encoding using this dropdown. Valid options include [!UICONTROL UTF-8] and [!UICONTROL Latin1].
  * **[!UICONTROL List delimiter]**: Select the correct list delimiter. If using a downloaded file or template file, make sure that the [!UICONTROL List delimiter] here matches the [!UICONTROL List delimiter] when the file was downloaded.
  * **[!UICONTROL Apply]**: Save the uploaded classification data to the Classification Set.

  ![Classification Set upload](../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Download key values and their classification columns.
  * **[!UICONTROL Rows]**: The maximum number of rows to include in the download file.
  * **[!UICONTROL Download rows received between]**: A calendar date picker that allows you to filter key values by when they appear in reporting. If a key value was not collected in this date range, it does not appear in the downloaded file.
  * **[!UICONTROL Data returned]**: A dropdown that lets you filter key values included in the downloaded file based on their associated classification data.
    * **[!UICONTROL All classified values]**: Includes rows where classification data is included in at least one column.
    * **[!UICONTROL All unclassified values]**: Includes rows where classification data is missing in at least one column.
  * **[!UICONTROL File format]**: Dropdown that determines the file format that the download file is in. Options include [!UICONTROL JSON], [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: Dropdown that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.
  * **[!UICONTROL List delimiters]**: Dropdown that determines the list delimiter separating classification columns on each row.

  ![Classification Set download](../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Download a template file. This file is similar to the [!UICONTROL Download] button, except it does not contain any classification data or key values.
  * **[!UICONTROL File format]**: Dropdown that determines the file format that the template file is in. Options include [!UICONTROL Comma separated values], and [!UICONTROL Excel tab separated values].
  * **[!UICONTROL File encoding]**: Dropdown that determines the file encoding. Options include [!UICONTROL UTF-8] and [!UICONTROL Latin1]. UTF-8 is recommended.
  * **[!UICONTROL List delimiters]**: Dropdown that determines the list delimiter separating classification columns on each row.
* **[!UICONTROL Job history]**: A shortcut link that takes you to the [Job manager](job-manager.md), showing jobs only for this Classification Set.

  ![Classification Set template](../assets/classification-set-template.png)
