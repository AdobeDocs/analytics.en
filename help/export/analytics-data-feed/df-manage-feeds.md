---
title: Data feed UI
description: Learn how to navigate the data feed interface.
feature: Data Feeds
exl-id: 4d4f0062-e079-48ff-9464-940c6425ad54
---
# Manage data feeds

The data feed manager lets you create, edit, and delete data feeds for your organization. If you have permissions to access the data feed manager, you can manage data feeds for all report suites visible to you.

Here is a video on the Data Feeds Management UI:

>[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

Access Data feed management by following these steps:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Select the 9-square icon in the upper-right, then select [!UICONTROL **Analytics**].
1. In the top navigation bar, go to [!UICONTROL **Admin**] > [!UICONTROL **Data feeds**].

## Navigate the interface

When arriving to the data feed manager page, the interface looks similar to the following:

![Data feeds](assets/feeds.png)

If no feeds have been set up, the page shows a [!UICONTROL Create New Data Feed] button.

### Filters and search

Use search or filters to locate a specific feed.

* In the search field, begin typing the name of a feed. Only those feeds that match are shown in the list of available feeds.

* On the far left, click the filter icon to show or hide filtering options. Filters are organized by category. You can collapse or expand filtering categories. Select the checkbox next to any filter you want to apply.

  ![Filter](assets/filters.png)

### Feeds and Jobs

Select the [!UICONTROL **Jobs**] tab to view individual jobs that each of your feeds create. See [Manage data feed jobs](df-manage-jobs.md).

### Add

The [!UICONTROL Add] button allows you to create a new feed. See [Create a data feed](create-feed.md) for more information.

### Columns

Each created feed shows several columns providing information about it. Select a column header to sort it in ascending order. Select a column header again to sort it in descending order. If you cannot see a specific column, click the column icon in the top-right.

![Column icon](assets/cols.jpg)

* **Feed Name**: Required column. Displays the feed name.
* **Feed ID**: Displays the Feed ID, a unique identifier.
* **Report Suite**: The report suite the feed references data from.
* **Report Suite ID**: The report suite's unique identifier.
* **Data Columns**: Which data columns are active for the feed. In most cases, there are too many columns to display in this format.
* **Interval**: Indicator whether the feed is hourly or daily.
* **Destination Type**: The destination type for the feed. For example, Amazon S3, GCP, or Azure.
* **Destination Host**: The location the file is placed.
* **Owner**: The user account that created the feed.
* **Status**: The status of the feed.
  * Active: The feed is operational.
  * Approval Pending: In some circumstances, a feed requires approval by Adobe before it can start generating jobs.
  * Deleted: The feed is deleted.
  * Complete: The feed finished processing. A completed feed can be edited, put on hold, or cancelled.
  * Pending: The feed is created but not yet active. Feeds remain in this state for a short transitional time.
  * Inactive: Equivalent to a 'paused' or 'on hold' state. If a backfill feed (a feed that processes only historical data) is reactivated, it resumes delivering jobs from when it stopped. If a live feed is reactivated, it resumes delivering jobs from when it stopped.
* **Last Modified**: The date the feed was last modified. Date and time is shown in the report suite's time zone with GMT offset.
* **Start Date**: The date of the first job for this feed. Date and time is shown in the report suite's time zone with GMT offset.
* **End Date**: The date of the last job for this feed. Ongoing data feeds do not have an end date.

## Data feed actions

Click the checkbox next to a data feed to reveal available actions.

* **Job history**: View all jobs tied to this data feeds. Automatically takes you to the [manage jobs interface](df-manage-jobs.md).
* **Delete**: Deletes the data feed, setting its status to [!UICONTROL Deleted].
* **Copy**: Takes you to [create a new feed](create-feed.md) with all settings of the current feed. You cannot copy a data feed if more than one is selected.
* **Pause**: Stops processing for the feed, setting its status to [!UICONTROL Inactive].
* **Activate**: Only available for inactive feeds. Backfill feeds (feeds that process only historical data) resume processing data from where they stopped, backfilling any dates if necessary. Live feeds  resume processing data from the current time. 
