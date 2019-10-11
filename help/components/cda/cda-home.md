---
title: Cross-Device Analytics
description: Cross-Device Analytics changes your data from being device-focused to person-focused by stitching device data together.
---

# Cross-Device Analytics

> [!NOTE] Cross-Device Analytics documentation is subject to change as the feature is further developed. Check back regularly for updates.

Cross-Device Analytics is a feature that transforms Analytics from a device-centric view to a person-centric view. This feature uses the Adobe Experience Platform Identity Service Co-op Graph or Private Graph to identify which devices belong to individuals, and stitch them together. As a result, analysts can understand user behavior that crosses browsers, devices, or apps. Using CDA you can answer questions such as:
 
* How many people are interacting with my brand? How many and what types of devices do they use? How do they overlap?
* How often do people begin a task on a mobile device and then later move to a desktop PC to complete the task? Do campaign click-throughs that land on one device lead to conversion somewhere else?
* How does my understanding of campaign effectiveness change if I take into account cross-device journeys? How does my funnel analysis change?
* What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed?
* How does the behavior of users with multiple devices differ from the users with a single device?

When devices are stitched, variable persistence is carried over across devices. For example, a user first visits your site through an advertisement on their desktop computer. That user finds your mobile app, installs it, and eventually makes a purchase on their mobile device. With Cross-Device Analytics, revenue can be attributed to the ad they clicked on their desktop computer.

See [Journey IQ: Cross-Device Analytics Spark page](http://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## Prerequisites

As of September 2019, Cross-Device Analytics requires the following. Work with teams within your organization and your Adobe Account Manager to ensure that you meet all of the following.

> [!IMPORTANT] Failure to meet all prerequisites can result in the inability to enable Cross-Device Analytics or poor results when stitching data.

* Your organization's data must reside within Adobe's Pacific Northwest data center. Support for data centers in other regions of the world is planned.
* Contact your organization's Account Manager to establish these key points:
  * A contract must be signed with Adobe that includes Adobe Analytics Ultimate. 
  * Your organization must use the Adobe Experience Platform Identity Service Co-op Graph or Private Graph. See the [Home Page](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) in the Device Co-op user guide.
  * Your organization must agree to allow Adobe to process and store Analytics data on Microsoft Azure servers. Adobe uses Azure to store device graph data and perform device stitching. As such, Adobe Analytics data is passed back-and-forth between Adobe's data processing center and Adobe's presence in Microsoft Azure.
* Cross-Device Analytics is enabled on a per-report suite basis. Report suites that have been enabled for CDA require the following:
  * The report suite cannot have more than 100 million hits per day. This threshold will increase over the coming months.
  * Adobe recommends a report suite contains cross-device data, meaning data from multiple device types (web, app, etc). Some organizations refer to this concept as a "global" report suite, although CDA does not strictly have to be global from a geographic perspective. Cross-Device Analytics does not work across report suites, nor does it combine data from multiple report suites.
* Your implementation must meet the following requirements:
  * The latest version of the Experience Cloud ID Service must be deployed. See the [Home Page](https://docs.adobe.com/content/help/en/id-service/using/home.html) in the Experience Cloud Identity Service user guide. Most implementations using Adobe Experience Platform Launch likely already have ECID deployed.
  * Call the `setCustomerIDs` function whenever an individual can be identified, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. See [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) in the Experience Cloud Identity Service user guide.

## Limitations

Cross-Device Analytics is a groundbreaking and robust feature, but has limitations in how it can be used.

* CDA is only available through Analysis Workspace.
* Stitching cannot occur across report suites as described in the prerequisites above.
* Adobe Analytics report suites cannot map to more than one IMS org. Since CDA stitches devices within a given report suite, CDA cannot be used to stitch data across multiple IMS orgs.
* CDA is not currently compatible with Customer Attributes. Customer Attributes cannot be used to create a CDA virtual report suite, within cross-device segments, or for reporting within an Analysis workspace project that is based on a CDA virtual report suite.
* CDA requires either Co-op Graph or Private Graph. 3rd-party device graphs are not supported.
* Legacy Analytics ID's are not supported. Only visitors with Experience Cloud ID's are stitched.
* Customer Care does not yet fully support this feature. The [Cross-Device Analytics forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) can be used for support on this feature, which includes active and direct involvement from Adobe Product Managers.
* Cross-Device Analytics uses a virtual report suite and report time processing, which have their own limitations. See [Virtual report suites](../vrs/vrs-about.md) and [Report time processing](../vrs/vrs-report-time-processing.md) for more information on these limitations.
* New devices visiting your site can take up to two weeks to be processed by the Co-op Graph or Private graph. The level of stitching in CDA for the most recent two weeks is typically lower than for date ranges older than two weeks. Adobe plans to improve the Adobe Experience Platform Identity Service to stitch new devices real-time in the future.
* Historical data in the virtual report suite changes based on Adobe recognizing and stitching devices together. Data in the source report suite does not change.

Once your organization has all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](cda-setup.md).
