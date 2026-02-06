---
title: Manage Data Feed Jobs
description: Learn how to manage individual jobs in data feeds. Navigate the interface, use filters and search, and find column definitions.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
---
# Manage data feed jobs

Jobs are individual tasks that output a compressed file. They are created and governed by feeds.

You can view the job history for each data feed, resend jobs, or reprocess jobs. 

## View job history for a data feed

You can view a list of data feed jobs for a given data feed, along with information about each job.

To view job history for a data feed:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.

1. Select the 9-square icon in the upper-right, then select [!UICONTROL **Analytics**].

1. In the top navigation bar, go to [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

   Data feeds for all report suites that you have access to are displayed. Or, if no feeds have been configured, the page shows a **[!UICONTROL Create data feed]** button.

   ![Data feed manager](assets/data-feed-manager.png)

1. Select the checkbox next to the data feed that contains the jobs that you want to view, then select [!UICONTROL **Job history**].

   Data feed job history is shown, with information about each job in the available columns.

1. (Optional) To adjust the visible columns in the table select the column icon ![Column icon](assets/customize-columns-icon.png) in the top-right, then in the Customize table dialog, select each column you want to view and deselect each column you want to hide.

   The following columns are available:

   * **[!UICONTROL Request period begin]**

   * **[!UICONTROL Request period end]**

   * **[!UICONTROL Scheduled]**

   * **[!UICONTROL Started]**

   * **[!UICONTROL Finished]**

   * **[!UICONTROL Run #]**

   * **[!UICONTROL Status]**

   * **[!UICONTROL Error code]**

   * **[!UICONTROL Error message]**

## Resend data feed jobs

When you resend a data feed job, it sends the data feed file again with the same data and processing as when the file was originally sent. Alternatively, you can [reprocess a data feed job](#reprocess-data-feed-jobs).

To resend one or more data feed jobs:

1. In Adobe Analytics, select [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

1. Select the checkbox next to the data feed that contains the jobs that you want to resend, then select [!UICONTROL **Job history**].

1. Select the checkbox next to one or more data feed jobs, then select **[!UICONTROL Resend]**. <!-- What does the status need to be? Error, ... -->

   ![Reprocess data feed job](assets/data-feed-job-resend.png)

## Reprocess data feed jobs

When you reprocess a data feed job, it reprocesses the source data of a data feed job and sends it again with the reprocessed data. Alternatively, you can [resend a data feed job](#resend-data-feed-jobs).

To reprocess one or more data feed jobs:

1. In Adobe Analytics, select [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

1. Select the checkbox next to the data feed that contains the jobs that you want to reprocess, then select [!UICONTROL **Job history**].

1. Select the checkbox next to one or more data feed jobs, then select **[!UICONTROL Reprocess]**. <!-- What does the status need to be? Error, ... -->

   ![Reprocess data feed job](assets/data-feed-job-reprocess.png)
