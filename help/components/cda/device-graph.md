---
title: Setting up Cross-Device Analytics
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
---

# Device graph

Explain what it is

Why it's valuable

(have separate co-op and private graph sections where they differ)

## Device graph specific Prerequisites 

Cross-Device Analytics requires the following. Work with teams within your organization and your Adobe Account Manager to ensure that you meet all of the following.

>[!IMPORTANT] Failure to meet all prerequisites can result in the inability to enable Cross-Device Analytics or poor results when stitching data.

* All prerequisites listed on the [overview page](overview.md).
* Your organization's data must reside within Adobe's Pacific Northwest data center. Support for data centers in other regions of the world is planned.
* Contact your organization's Account Manager to establish these key points:
  * A contract must be signed with Adobe that includes Adobe Analytics Ultimate.
  * Your organization must use the Adobe Experience Platform Identity Service Co-op Graph or Private Graph. See the [Home Page](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) in the Device Co-op user guide.
  * Out of a spirit of partnership and transparency, we want our customers to be aware of our use of Microsoft Azure in association with Cross-Device Analytics. Adobe uses Azure to store device graph data and to perform cross-device stitching. As such, Adobe Analytics data is passed back-and-forth between Adobe's data processing center and Adobe’s provisioned instances of Microsoft Azure.
* Cross-Device Analytics is enabled on a per-report suite basis. Report suites enabled for CDA require the following:
  * The report suite cannot have more than 500 million hits per day.
  * Adobe recommends a report suite contains cross-device data, meaning data from multiple device types (web, app, etc). Some organizations refer to this concept as a "global" report suite, although CDA does not strictly have to be global from a geographic perspective. Cross-Device Analytics does not work across report suites, nor does it combine data from multiple report suites.
* Your implementation must meet the following requirements:
  * The latest version of the Experience Cloud ID Service must be deployed. See the [Home Page](https://docs.adobe.com/content/help/en/id-service/using/home.html) in the Experience Cloud Identity Service user guide. Most implementations using Adobe Experience Platform Launch likely already have ECID deployed.
  * Call the `setCustomerIDs` function whenever an individual can be identified, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. See [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) in the Experience Cloud Identity Service user guide.



## Device graph-specific limitations

* Legacy Analytics ID's are not supported. Only visitors with Experience Cloud ID's are stitched.
* If your organization uses the Private Graph, new devices take up to 24 hours to be stitched. 
* New devices visiting your site can take up to two weeks to be processed by the Co-op Graph. The level of stitching in CDA for the most recent two weeks is typically lower than for date ranges older than two weeks.
* 3rd-party device graphs are not supported.



Once your organization has all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](cda-setup.md).

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. You must belong to a Product Profile Admin group or have admin privileges in Adobe Analytics to follow these steps.

>[!IMPORTANT] All prerequisites must be met before following these steps. If all prerequisites are not met, the feature is not available or will not work. See [Cross-Device Analytics](cda-home.md) for prerequisites and limitations.

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

