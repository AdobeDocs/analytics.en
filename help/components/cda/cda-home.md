---
title: Cross-Device Analytics
description: Cross-Device Analytics changes your data from being device-focused to person-focused by stitching device data together.
---

# Cross-Device Analytics

Cross-Device Analytics is a feature within Journey IQ that transforms Analytics from a device-centric view to a person-centric view. This feature uses the Adobe Experience Platform Identity Service Co-op Graph or Private Graph to identify which devices belong to individuals, and stitch them together. As a result, analysts can understand the impact that behavior has between browsers, devices, or apps.

When devices are stitched, variable persistence is carried over across devices. For example, a user first visits your site through an advertisement on their desktop computer. That user finds your mobile app, installs it, and eventually makes a purchase on their mobile device. With Cross-Device Analytics, revenue can be attributed to the ad they clicked on their desktop computer.

See [Journey IQ: Cross-Device Analytics Spark page](https://spark.adobe.com/page/8ZpjsX6Lp5XTM/) to learn more about the capabilities and features of Cross-Device Analytics.

## Prerequisites

Cross-Device Analytics requires the following. Work with teams within your organization and your Adobe Account Manager to ensure you meet all of the following.

> [!IMPORTANT] Failure to meet all prerequisites results in the inability to enable Cross-Device Analytics, or the feature not stitching data.

* Your organization's data must reside within Adobe's Pacific Northwest data center. Support for other data centers is planned.
* Contact your organization's Account Manager to establish these key points:
  * A contract must be signed with Adobe that includes Adobe Analytics Ultimate. Your account manager can help update your organization's contract with Adobe.
  * You must belong to either the Adobe Experience Platform Identity Service Co-op Graph or Private Graph. Your account manager can start the provisioning process for either of these services. See the [Home Page](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) in the Device Co-op user guide.
  * Legal and privacy requirements must be acknowledged, including the processing and storage of data on Microsoft Azure servers.
* Cross-Device Analytics is enabled on a per-report suite basis. Your report suite requires the following:
  * At this time, a report suite cannot have more than 100 million hits per day. This threshold will increase as Cross-Device Analytics is further developed.
  * All data across devices must be sent to the same report suite. Some organizations employ a global report suite, which is valid in this context. Cross-Device Analytics does not work across report suites.
* Your implementation must meet the following requirements:
  * The latest version of the Experience Cloud ID Service must be deployed. See the [Home Page](https://docs.adobe.com/content/help/en/id-service/using/home.html) in the Experience Cloud Identity Service user guide. Most implementations using Adobe Experience Platform Launch likely already have ECID deployed.
  * Call the `setCustomerIDs` function whenever an individual can be identified, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. See [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) in the Experience Cloud Identity Service user guide.

## Limitations

Cross-Device Analytics is a groundbreaking and robust feature, but has limitations in how it can be used.

* Stitching cannot occur across IMS organizations. Make sure that you are not using multiple IMS Orgs in your implementation.
* Legacy Analytics ID's are not supported. Only Experience Cloud ID's can use Cross-Device Analytics.
* Customer Care does not yet support this feature. The [Cross-Device Analytics forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) can be used for support on this feature, which includes active and direct involvement from Adobe Product Managers.
* Cross-Device Analytics heavily relies on virtual report suites, and therefore inherits all limitations from them. See [Virtual report suites](../vrs/vrs-about.md) for more information.
* While existing known devices are stitched and shown within hours, new devices visiting your site can take up to two weeks to fully stitch. Adobe plans to improve the Adobe Experience Platform Identity Service to stitch new devices real-time in the future.
* Historical data in the virtual report suite changes based on Adobe recognizing and stitching devices together. Data in the source report suite does not change.

Once your organization has all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](cda-setup.md).
