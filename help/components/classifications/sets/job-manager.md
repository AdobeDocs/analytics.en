---
title: Classification Jobs Manager
description: Learn how to view current and completed classification jobs that are generated from classification sets.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
TQID: https://experienceleague.adobe.com/KXJHotem9uyppKE-oZ4KsOn1c2BOVDY2jepu6GR3DK4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# View and act upon classification jobs

The Classification jobs manager shows current and completed classification jobs that are generated for classification sets. You can also use the manager to download classification data or templates for a particular job.

To view and act upon classification jobs:


1. Select **[!UICONTROL Components]** from the Adobe Analytics top menu bar, then select **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, select the **[!UICONTROL Jobs]** tab.

## Classification jobs manager

The **[!UICONTROL Classification Sets - Jobs]** manager has the following interface elements:

![Classifications Sets - Job Manager](manage/assets/classifications-sets-jobs.png)



### Classification jobs list

The **[!UICONTROL Classification Jobs]** list ➊ displays classification jobs. The list has the following columns:

| Column | Description |
|---|---|
| **[!UICONTROL Job Id]** | The identifier of the classification job. |
| **[!UICONTROL Classification Set]** | The classification set associated with the classification job. |
| **[!UICONTROL Size]** | The size of the file that was exported or imported as part of the classification job.  |
| **[!UICONTROL Status]** | The status of the classification job. Possible values are: **[!UICONTROL Created]**, **[!UICONTROL Queued]**, **[!UICONTROL Validated]**, **[!UICONTROL Failed validation]**, **[!UICONTROL Processing]**, **[!UICONTROL Done processing]**, **[!UICONTROL Failed processing]** , **[!UICONTROL Completed]**, or **[!UICONTROL Progress]**. If displayed, hover over the alert ![Alert](/help/assets/icons/Alert.svg) to display additional information. |
| **[!UICONTROL File Name]** | Identifies the name or functionality used to import or export the file as part of the classification job. Possible values are: <ul><li>*no value*</li><li>The name of the file that is processed as part of the classification job.</li><li>**[!UICONTROL SAINT Export]**: The job is an export from the [legacy Classifications interface](/help/components/classifications/importer/c-working-with-saint.md).</li><li>**[!UICONTROL export for _classification set_ at _timestamp_]**: The job is a download from the [schema](manage/schema.md#download) interface.</li></ul> |
| **[!UICONTROL Job Type]** | The type of classification job. Possible values are: **[!UICONTROL Import]** or **[!UICONTROL Export]**. |
| **[!UICONTROL Source]** | The source of the classification job. See [Filter panel](#filter-panel) for details on possible sources. |
| **[!UICONTROL Modified Lines]** | The number of modified lines that the classification job modified. |
| **[!UICONTROL Total Lines]** | The number of total lines that the classification job processed. |
| **[!UICONTROL Completion Time]** | The completion time of the classification job. |
| **[!UICONTROL File Download]** | Use ![Download](/help/assets/icons/Download.svg) to download the file (template or data) associated with the classification job. |

To resize a column in the classification jobs list, you can:

* Hover over the column separator and drag the column separator to the desired column width.
* Select ![ChevronDown](/help/assets/icons/ChevronDown.svg) and select **[!UICONTROL Resize column]**. A vertical line with resize button allows you to resize the column to the desired with.

To sort a column in the classification jobs list

* Select ![ChevronDown](/help/assets/icons/ChevronDown.svg) and select **[!UICONTROL Sort Ascending]** or **[!UICONTROL Sort Descending]**. An arrow (↑↓) indicates which column and how the column is sorted.


### Search and buttons

In the area ➋ on top of the classification jobs list, you can:

* Search ![Search](/help/assets/icons/Search.svg) for classification jobs. Results are shown in the classification jobs list. Select ![CrossSize200](/help/assets/icons/CrossSize200.svg) to clear the search.
* Remove any filter that is applied to the classification jobs list. Select ![CrossSize100](/help/assets/icons/CrossSize100.svg) to remove a filter.
* Select ![MoreCircle](/help/assets/icons/MoreCircle.svg) to load an addition 1000 classification jobs. Initially, the classification set list displays up to 1000 classification jobs. 
* Define the columns of the classification sets jobs list. Select ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) and in the **[!UICONTROL Customize table]** dialog select the columns to show underneath **[!UICONTROL Select columns to show]**. Select **[!UICONTROL Apply]** to apply the column settings.



### Filter panel

Select ![Filter](/help/assets/icons/Filter.svg) to show the filter panel ➌ that allows you to filter the classification jobs list. You can filter on:

* **[!UICONTROL Classification Set]**. Select one or more classification sets to filter the classification jobs list.
* **[!UICONTROL Completion Time]**. Select one of the possible values to filter the classification jobs list on completion time.
* **[!UICONTROL Status]**. Select one of the possible values to filter the classification jobs list on status. 
* **[!UICONTROL Job Type]**. Select one of the possible values to filter the classification jobs list on job type. 
* **[!UICONTROL Source]**. Select one of the possible values to filter the classification jobs list on source.
  
  Possible values for **[!UICONTROL Source]** are:

  | Source | Explanation |
  |---|---|
  | **[!UICONTROL Adobe]** | Jobs created by Adobe as part of an internal process. For example, consolidations. |
  | **[!UICONTROL Backend]** | Jobs created by the deprecated FTP import process. |
  | **[!UICONTROL Cloud Ingestion]** | Jobs that are the result of importing classification data from a cloud location. |
  | **[!UICONTROL Direct API Export]** | Jobs that are the result of using the Adobe Analytics 2.0 API to export classification data. |
  | **[!UICONTROL Direct API Upload]** | Jobs that are the result of using the Adobe Analytics 2.0 API to upload classification data. |
  | **[!UICONTROL Republish]** | Jobs that are the result of a republish. |
  | **[!UICONTROL Rule-based Classifications]** | Jobs that are the results of rule-based classifications. |
  | **[!UICONTROL Saint]** | Jobs that are the results of legacy rule-based classifications. |
  | **[!UICONTROL Web API]** | Jobs that are the results of using the Web API to export or upload classification data. |
  | **[!UICONTROL Unknown]** | Jobs for which the source is unknown. |


Select ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** to hide the filters panel.

Note that the filters shown in the filters panel reflect the options for the classification jobs that are preloaded.
