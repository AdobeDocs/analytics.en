---
description: Guidelines for specifying the output format.
seo-description: Guidelines for specifying the output format.
seo-title: Output format
solution: Analytics
title: Output format
topic: Data workbench
uuid: 65440fa6-b123-4e11-8baa-467e55b15166
index: y
internal: n
snippet: y
---

# Output format

Guidelines for specifying the output format.

* Each metric or dimension name must start and end with a percent sign (%).

    * %XYZ% specifies the element of dimension XYZ corresponding to the element of Level. An error is generated if dimension XYZ is not one-to-one or one-to-many with Level. 
    * %=XYZ% specifies the value of metric or metric formula XYZ for the given element of Level.

* Dimension names that are two words or longer do not require underscores. 
* Metric names that are two words or longer require underscores.

>[!NOTE]
>
>If you hold down the Ctrl key and right-click within the [!UICONTROL Output Format] field, an [!UICONTROL Insert menu] appears. This menu contains a list of special characters (for example, Tab) that often are used as delimiters.

If you want to export session duration data for your segment, you must create a new metric based on the Session Duration metric. The new metric, which is for use only with the [!UICONTROL Output Format] field of segment export, enables Microsoft Excel to correctly interpret sessions lasting less than one hour. To create a new session duration metric, open the [!DNL Session Duration.metric] file (from the [!UICONTROL Profile Manager]) and insert a pound sign (#) into the ftime string: [!DNL ftime = string: %#H:%M:%S]

The pound sign causes a leading “0” to be appended to session durations of less than 1 hour. As a result, Excel interprets 0:53:21 as 53 minutes and 21 seconds. Save the new metric with a different name and upload it to the appropriate profile for others to use by right-clicking the check mark for the file in the [!UICONTROL User] column and clicking **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*. 
