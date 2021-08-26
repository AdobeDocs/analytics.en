---
title: Cross-Device Analytics
description: Change your data from device-focused to person-focused by stitching device data together.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
---
# Cross-Device Analytics

Cross-Device Analytics is a feature that transforms Analytics from a device-centric view to a person-centric view. As a result, analysts can understand user behavior that crosses browsers, devices, or apps. Adobe supports two overarching workflows to link device data together:

* [**Field-based stitching**](field-based-stitching.md): Allows you to choose an Analytics variable as a base for cross-device stitching in a virtual report suite. Uses deterministic matching to link devices together. Adobe recommends using field-based stitching for most deterministic matching use cases.
* [**Device graph**](device-graph.md): CDA communicates with a device graph to stitch devices together. The co-op graph uses both deterministic and probabilistic matching.

Using CDA, you can answer questions such as:

* How many people interact with my brand? How many and what types of devices do they use? How do they overlap?
* How often do people begin a task on a mobile device and then later move to a desktop PC to complete the task? Do campaign click-throughs that land on one device lead to conversion somewhere else?
* How does my understanding of campaign effectiveness change if I take into account cross-device journeys? How does my funnel analysis change?
* What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed?
* How does the behavior of users with multiple devices differ from the users with a single device?

When devices are stitched, variable persistence is carried over across devices. For example, a user first visits your site through an advertisement on their desktop computer. That user finds your mobile app, installs it, and eventually makes a purchase on their mobile device. With Cross-Device Analytics, you can attribute revenue on the mobile device to the ad that they clicked on their desktop computer.

Out of a spirit of partnership and transparency, we want our customers to be aware of our use of Microsoft Azure in association with Cross-Device Analytics. Adobe uses Azure to store device graph data and to perform cross-device stitching. As such, Adobe Analytics data is passed back-and-forth between Adobe's data processing center and Adobe’s provisioned instances of Microsoft Azure.

See the [Journey IQ: Cross-Device Analytics Spark page](https://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## Prerequisites

The use of CDA requires all of the following. [Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md) methods also have their own specific prerequisites.

* A contract must be signed with Adobe that includes Adobe Analytics Ultimate.
* Cross-Device Analytics is enabled on a per-report-suite basis. Adobe recommends a report suite that contains cross-device data, meaning data from multiple device types (web, app, etc). Some organizations refer to this concept as a "global" report suite, although CDA does not strictly have to be global from a geographic perspective. 

## Limitations

Cross-Device Analytics is a groundbreaking and robust feature, but has limitations in how it can be used. [Field-based stitching](field-based-stitching.md) and [Device graph](device-graph.md) methods also have their own specific limitations.

* CDA is only available through Analysis Workspace.
* Cross-Device Analytics does not work across report suites, nor does it combine data from multiple report suites.
* Adobe Analytics report suites cannot map to more than one IMS org. Since CDA stitches devices within a given report suite, CDA cannot be used to stitch data across multiple IMS orgs.
* Private Graph leverages the same ID syncs as those used by the [Customer Attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=en#customer-attributes) capability found within Experience Cloud and Adobe Analytics. However, CDA virtual report suites (whether based on private graph or field-based stitching) are not compatible with the rest of the Customer Attributes functionality. That is, Customer Attributes-based dimensions are not available for use within CDA virtual report suites.
* CDA is not currently compatible with A4T.
* Cross-Device Analytics uses a virtual report suite and report time processing, which have their own limitations. See [Virtual report suites](../vrs/vrs-about.md) and [Report time processing](../vrs/vrs-report-time-processing.md) for more information on these limitations.
* The 1.4 API is not supported. Power BI connectors and Report Builder both rely on the 1.4 API, and are therefore not compatible with CDA.
* Historical data in the virtual report suite changes based on Adobe recognizing and stitching devices together. Data in the source report suite does not change.
* Active monitoring of the CDA stitching process by Adobe is limited to production report suites only.
* CDA is not currently compatible with the Adobe Analytics [Data Repair API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md)
