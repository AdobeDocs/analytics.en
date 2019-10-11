---
title: Setting up Cross-Device Analytics
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
---

# Setting up Cross-Device Analytics

> [!NOTE] Cross-Device Analytics documentation is subject to change as the feature is further developed. Check back regularly for updates.

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. You must belong to a Product Profile Admin group or have admin privileges in Adobe Analytics to follow these steps.

> [!IMPORTANT] All prerequisites must be met before following these steps. If all prerequisites are not met, the feature is not available or will not work. See [Cross-Device Analytics](cda-home.md) for prerequisites and limitations.

## Choose the cross-device report suite that will be enabled for CDA

When your organization is provisioned to use CDA, you choose which report suite to use. This choice can be communicated through your Adobe Account Manager. Adobe then enables your chosen report suite for CDA processing.

## Create a cross-device virtual report suite to see the cross-device view

Administrators with access to create virtual report suites can create CDA virtual report suites as follows:

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
2. Click the 9-grid icon at the top, then click Analytics.
3. Hover over Components at the top, then click Virtual Report Suites.
4. Click Add.
5. Enter a name for your virtual report suite, and ensure that the CDA-enabled report suite is selected. You may optionally apply a segment to the virtual report suite. For example, you may want to apply a segment that limits the virtual report suite to dates after CDA was turned on and stitching began. This way, users will see only stitched date ranges within the VRS.
6. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
7. Click the checkbox 'Stitch User Visits Across Devices'.
8. Click Continue, finish configuring the virtual report suite, then click Save.

![CDA checkbox](assets/cda-checkbox.png)

## Additions and changes to cross-device virtual report suites

When Cross-Device Analytics is enabled on a virtual report suite, note the following changes:

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* New metrics labeled 'People' and 'Unique Devices' are available.
* The metric 'Unique Visitors' is not available, as it is replaced with People and Unique Devices.
* When building segments, the 'Visitor' segment container is replaced with a 'Person' container.

## The Compression calculated metric

The ability for Cross-Device Analytics to stitch devices together depends on a wide range of factors. The effectiveness of the feature's ability to stitch data can be measured with a calculated metric called compression. Factors that contribute to compression include:

* Using the Co-op graph or Private graph: Generally speaking, organizations using the device co-op tend to see better compression rates than organizations using the private graph.
* Log in rate: The more users log in on your site, the more Adobe can identify and stitch visitors across devices. Sites with a low log in rate also have low compression rates.
* Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
* Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
* Reporting granularity: Compression by day is typically smaller than compression by month or year. The chances for an individual to use multiple devices becomes smaller within a single day than over an entire month. Segmenting, filtering, or using breakdown dimensions can also show a lower compression rate.

To see your organization's compression for a given time period:

1. Click Workspace at the top, then click 'Create New Project'.
2. Start with a Blank Project, then click Create.
3. Drag the Unique Devices metric onto the canvas area labeled 'Drop a Metric Here'.
4. Drag the People metric onto the canvas directly to the right of the Unique Devices metric header, so the two metrics are side-by-side.
5. Click the '`+`' symbol next to available metrics on the left to open the Calculated Metric builder.
6. Give this calculated metric the following settings:
   * Name: Cross-Device Compression
   * Format: Percent
   * Decimal Places: 2
   * Definition: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Click 'Add' in the top right corner of the definition area to add a static number. Drag People and Unique Devices from the list of available metrics on the left.
7. Click Save.
8. Drag the new calculated metric onto the canvas directly to the right of the People metric header, so all three metrics are side-by-side.
9. Optional: The workspace loads the Day dimension by default. Drag an alternate date dimension, such as week or month, on top of the Day dimension if a different time granularity is desired.
