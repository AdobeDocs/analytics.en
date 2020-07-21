---
title: Set up Cross-device Analytics
description: Configure a virtual report suite to enable CDA.
---

# Set up Cross-device Analytics

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. You must belong to a Product Profile Admin group or have admin privileges in Adobe Analytics to follow these steps.

>[!IMPORTANT] All prerequisites must be met before following these steps. If all prerequisites are not met, the feature is not available or will not work. See the [overview page](overview.md) and the desired stitching method ([Field-based stitching](field-based-stitching.md) or [Device graph](device-graph.md), respectively) for prerequisites and limitations.

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
