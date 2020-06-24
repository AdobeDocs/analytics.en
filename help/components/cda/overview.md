---
title: Cross-Device Analytics
description: Cross-Device Analytics changes your data from being device-focused to person-focused by stitching device data together.
---

<!-- Intro paragraph that lists the value of the tool and the 2 methods: field-based stitching and co-op/private graph-->

# Cross-Device Analytics

Cross-Device Analytics is a feature that transforms Analytics from a device-centric view to a person-centric view. This feature uses the Adobe Experience Platform Identity Service Co-op Graph or Private Graph to identify which devices belong to individuals, and stitch them together. As a result, analysts can understand user behavior that crosses browsers, devices, or apps. Using CDA you can answer questions such as:

* How many people interact with my brand? How many and what types of devices do they use? How do they overlap?
* How often do people begin a task on a mobile device and then later move to a desktop PC to complete the task? Do campaign click-throughs that land on one device lead to conversion somewhere else?
* How does my understanding of campaign effectiveness change if I take into account cross-device journeys? How does my funnel analysis change?
* What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed?
* How does the behavior of users with multiple devices differ from the users with a single device?

When devices are stitched, variable persistence is carried over across devices. For example, a user first visits your site through an advertisement on their desktop computer. That user finds your mobile app, installs it, and eventually makes a purchase on their mobile device. With Cross-Device Analytics, revenue can be attributed to the ad they clicked on their desktop computer.

See [Journey IQ: Cross-Device Analytics Spark page](http://adobe.ly/aacda) to learn more about the capabilities and features of Cross-Device Analytics.

## Prerequisites

* List all the prerequisites required for both device graph and field based stitching

## Limitations

Cross-Device Analytics is a groundbreaking and robust feature, but has limitations in how it can be used. Field based stitching and device graph methods will also have their own specific limitations.

* CDA is only available through Analysis Workspace.
* Stitching cannot occur across report suites as described in the prerequisites above.
* Adobe Analytics report suites cannot map to more than one IMS org. Since CDA stitches devices within a given report suite, CDA cannot be used to stitch data across multiple IMS orgs.
* CDA is not currently compatible with Customer Attributes. Customer Attributes cannot be used to create a CDA virtual report suite, within cross-device segments, or for reporting within an Analysis workspace project that is based on a CDA virtual report suite.
  > [!TIP] Although Customer Attributes cannot be used in CDA, both features rely on the `setCustomerIDs` function. These two features can coincide in separate virtual report suites.
* Cross-Device Analytics uses a virtual report suite and report time processing, which have their own limitations. See [Virtual report suites](../vrs/vrs-about.md) and [Report time processing](../vrs/vrs-report-time-processing.md) for more information on these limitations.
* The 1.4 API is not supported. Power BI connectors and Report Builder both rely on the 1.4 API, and are therefore not compatible with CDA.
* Historical data in the virtual report suite changes based on Adobe recognizing and stitching devices together. Data in the source report suite does not change.

## Links to each method

* [Field-based stitching:](field-based-stitching.md) short description
* [Device graph:](device-graph.md) Short description
