---
title: Classification Set Job Manager
description: View current and completed classification jobs generated from Classification Sets.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
---
# Classification Set Jobs Manager

The Classification Set Job Manager lets you see current and completed classification jobs that were generated from Classification Sets. You can also use this interface to download classification data or templates for a particular job, or upload additional data to a job.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

Note that you cannot create jobs from this interface. Instead, you can create jobs by uploading data to a Classification Set, requesting a download file, or requesting a template file.

## Filter Classification Sets

The left side of the Classification Set Job Manager provides filter settings to locate the desired Job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification Sets by **[!UICONTROL Classification Set]**, **[!UICONTROL Completion time]**, or **[!UICONTROL Status]**.

![Classification Set Job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification Set Job Manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification Set Job Manager initially displays up to 1000 jobs. Click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification Set Job Manager columns

The following columns are available in the Classification Set Job Manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification Set]**: The name of the Classification Set that the file applies to. You can click on the Classification Set name to reach the Classification Set's [Settings](settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Type]**: The type of job.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
