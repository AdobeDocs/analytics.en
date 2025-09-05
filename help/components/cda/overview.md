---
title: Cross-Device Analytics
description: Learn how to change your data from device-focused to person-focused by stitching device data together.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
---
# Cross-Device Analytics

{{available-existing-customers}}

Cross-Device Analytics (CDA) is a feature that transforms Analytics from a device-centric view to a person-centric view. As a result, analysts can understand user behavior that crosses browsers, devices, or apps. Adobe supports two overarching workflows to link device data together:

* [**Field-based stitching**](field-based-stitching.md): Recommended stitching option because it uses only deterministic matching to link devices together.
Field-based stitching allows you to choose an Analytics variable as a base for cross-device stitching in a virtual report suite.

* [**Device graph**](device-graph.md): Cross-Device Analytics communicates with a private graph to stitch devices together.

Using CDA, you can answer questions such as:

* How many people interact with my brand? How many and what types of devices do they use? How do they overlap?
* How often do people begin a task on a mobile device and then later move to a desktop PC to complete the task? Do campaign click-throughs that land on one device lead to conversion somewhere else?
* How does my understanding of campaign effectiveness change if I take into account cross-device journeys? How does my funnel analysis change?
* What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed?
* How does the behavior of users with multiple devices differ from the users with a single device?

When devices are stitched, variable persistence is carried over across devices. For example, a user first visits your site through an advertisement on their desktop computer. That user finds your mobile app, installs it, and eventually makes a purchase on their mobile device. With Cross-Device Analytics, you can attribute revenue on the mobile device to the ad that they clicked on their desktop computer.

Microsoft Azure is used for Cross-Device Analytics. Adobe uses Azure to store device graph data and to perform cross-device stitching. As such, Adobe Analytics data is passed back-and-forth between Adobe's data processing center and Adobe's provisioned instances of Microsoft Azure.

See the [Cross-Device Analytics Spark page](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) to learn more about the capabilities and features of Cross-Device Analytics.

## Prerequisites

The use of Cross-Device Analytics requires [Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md) methods, and both have their own specific prerequisites.

* A contract must be signed with Adobe that includes Adobe Analytics Ultimate.
* Your organization chooses which report suites to enable CDA. Adobe recommends report suites that contain cross-device data, meaning data from multiple device/browser/app types. Some organizations refer to this concept as a "global" report suite, although Cross-Device Analytics does not strictly have to be global from a geographic perspective. 

## Limitations

Cross-Device Analytics is a groundbreaking and robust feature, but has limitations in how it can be used. [Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md) methods also have their own specific limitations.

* Cross-Device Analytics is only available through Analysis Workspace.
* Cross-Device Analytics does not work across report suites, nor does it combine data from multiple report suites.
* Adobe Analytics report suites cannot map to more than one organization ID. Since Cross-Device Analytics stitches devices within a given report suite, Cross-Device Analytics cannot be used to stitch data across multiple organization IDs.
* Cross-Device Analytics uses a complex processing pipeline, with multiple dependent components. This pipeline runs in parallel with the base Analytics reporting workflow. You can expect a data mismatch of approximately 1% for the total number of hits between the original report suite and the Cross-Device Analytics virtual report suite.
* Cross-Device Analytics uses a virtual report suite and report time processing, which have their own limitations. For example, they do not currently support Marketing Channels variables. See [Virtual report suites](/help/components/vrs/vrs-about.md) and [Report time processing](/help/components/vrs/vrs-report-time-processing.md) for more information on these limitations.
* Private Graph leverages the same ID syncs as the ID syncs used by the [Customer attributes](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) capability found within Experience Cloud and Adobe Analytics. However, Cross-Device Analytics virtual report suites (whether based on private graph or field-based stitching) are not compatible with the rest of the Customer attributes functionality. In other words, Customer attributes-based dimensions are not available for use with Cross-Device Analytics virtual report suites.
* Cross-Device Analytics is not currently compatible with A4T.
* The 1.4 API is not supported. Power BI connectors and Report Builder both rely on the 1.4 API, and are therefore not compatible with CDA.
* Active monitoring of the Cross-Device Analytics stitching process by Adobe is limited to production report suites only.
* Cross-Device Analytics is not currently compatible with the Adobe Analytics [Data Repair API](https://developer.adobe.com/analytics-apis/docs/2.0/)
* Historical data in the virtual report suite changes based on Adobe recognizing and stitching devices together. Data in the source report suite does not change.
* Stitched data follows a latency of 8 to 12 hours.
* Mapping history data for a given device is stored for up to 1 year.
* If a device reaches a very high number of mapping history entries within a year, the mapping history is truncated. The exact limit depends on the stitching option used.
