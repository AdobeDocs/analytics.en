---
title: Setting up Cross-Device Analytics
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
---

# Setting up Cross-Device Analytics

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. You must belong to a Product Profile Admin group or have admin privileges in Adobe Analytics to follow these steps.

>[!IMPORTANT]
>
>All prerequisites must be met before following these steps. If all prerequisites are not met, the feature is not available or will not work. See [Cross-Device Analytics](cda-home.md) for prerequisites and limitations.

## Choose the cross-device report suite that will be enabled for CDA

When your organization is provisioned to use CDA, you choose which report suite to use. This choice can be communicated through your Adobe Account Manager. Adobe then enables your chosen report suite for CDA processing.

## Create a cross-device virtual report suite to see the cross-device view

Administrators with access to create virtual report suites can create CDA virtual report suites as follows:

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
2. Click the 9-grid icon at the top, then click Analytics.
3. Hover over Components at the top, then click Virtual Report Suites.
4. Click Add.
5. Enter a name for your virtual report suite, and ensure that the CDA-enabled report suite is selected.
6. (Optional) Apply a segment to the virtual report suite. For example, you can apply a segment that limits the virtual report suite to dates after CDA was turned on and stitching began. This segment allows users to see only stitched date ranges within the VRS.
7. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
8. Click the checkbox 'Stitch User Visits Across Devices'.
9. Click Continue, finish configuring the virtual report suite, then click Save.

![CDA checkbox](assets/cda-checkbox.png)

## Additions and changes to cross-device virtual report suites

When Cross-Device Analytics is enabled on a virtual report suite, note the following changes:

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* A new dimension labeled 'Identified State' is available. This dimension determines if the Experience Cloud ID on that hit is known by the device graph at that time.
* New metrics labeled 'People' and 'Unique Devices' are available.
* The metric 'Unique Visitors' is not available, as it is replaced with 'People' and 'Unique Devices'.
* When building segments, the 'Visitor' segment container is replaced with a 'Person' container.

## CDA Workspace template

Adobe offers a template to see vital cross-device performance data.

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
1. Click the 9-grid icon at the top, then click Analytics.
1. Click [!UICONTROL Workspace] at the top, then click [!UICONTROL Create New Project].
1. Locate the "Journey IQ: Cross-Device Analytics" template, then click [!UICONTROL Create].
1. If prompted, change the report suite to one that supports CDA.

An Analysis Workspace project is created that contains several panels. At the top, a table of contents and introduction is shown, allowing context to the report and navigation to individual reports. Click a link within the table of contents or expand a panel's accordion to view those reports.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Special note for members of the Co-op Graph**: Shows what portion of your report suite contains visitors in regions where the co-op graph is supported, and regions where it is not supported.
* **Identification of users**: Shows how often visitors to your site are identified using methods based on Cross-Device Analytics. 
* **Measuring audience size**: Shows a comparison of 'Unique Devices' compared to 'People'. The proportion of these two numbers is known as 'Cross-device compression', a calculated metric visible in this panel. This compression metric depends on a broad range of factors:
  * Using the Co-op graph or Private graph: Generally speaking, organizations using the device co-op tend to see better compression rates than organizations using the private graph.
  * Log in rate: The more users log in on your site, the more Adobe can identify and stitch visitors across devices. Sites with a low log in rate also have low compression rates.
  * Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
  * Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
  * Reporting granularity: Compression by day is typically smaller than compression by month or year. The chances for an individual to use multiple devices becomes smaller within a single day than over an entire month. Segmenting, filtering, or using breakdown dimensions can also show a lower compression rate.
* **People-based segments**: Contains a segment dropdown that allows you to view device specific data. This panel encourages experimentation with segments to see how including or excluding device types affect reports.
* **Analyzing the cross-device journey**: Provides flow and fallout reports based on device type.
* **Cross-device attribution**: Combine the features of Journey IQ and Attribution IQ together.
* **Other tips and tricks**: Helpful topics around CDA that lets you get more out of using it.
