---
title: CDA Workspace template
description: Describes each field in the CDA template within Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
---
# CDA Workspace template

Adobe offers a template to see vital cross-device performance data.

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
1. Click the 9-grid icon at the top, then click Analytics.
1. Click [!UICONTROL Workspace] at the top, then click [!UICONTROL Create New Project].
1. Locate the "Cross-Device Analysis" template, then click [!UICONTROL Create].
1. If prompted, change the report suite to one that supports CDA.

An Analysis Workspace project is created that contains several panels. At the top, a table of contents and introduction is shown, allowing context to the report and navigation to individual reports. Click a link within the table of contents or expand a panel's accordion to view those reports.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identification of users**: Shows how often visitors to your site are identified using methods based on Cross-Device Analytics.
* **Measuring audience size**: Shows a comparison of 'Unique Devices' compared to 'People'. The proportion of these two numbers is known as 'Cross-device compression', a calculated metric visible in this panel. This compression metric depends on a broad range of factors:
  * Log in rate: The more users log in on your site, the more Adobe can identify and stitch visitors across devices. Sites with a low log in rate also have low compression rates.
  * Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
  * Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
  * Reporting granularity: Compression by day is typically smaller than compression by month or year. The chances for an individual to use multiple devices becomes smaller within a single day than over an entire month. Segmenting, filtering, or using breakdown dimensions can also show a lower compression rate.
* **People-based segments**: Contains a segment drop-down list that allows you to view device specific data. This panel encourages experimentation with segments to see how including or excluding device types affect reports.
* **Analyzing the cross-device journey**: Provides flow and fallout reports based on device type.
* **Cross-device attribution**: Combine the features of Journey IQ and Attribution IQ together.
* **Other tips and tricks**: Helpful topics around CDA that lets you get more out of using it.
