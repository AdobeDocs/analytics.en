---
title: Cross-Device Analytics FAQ
description: Frequently asked questions for Cross-Device Analytics
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
---
# Frequently asked questions

## How can I use CDA to see how people move from one device type to another?

You can use a [!UICONTROL Flow] visualization with the Mobile Device Type dimension.

1. Log in to Adobe Analytics and create a new blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Mobile Device Type' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

## Can I see how people move between different user experiences (e.g. desktop browser vs. mobile browser vs. mobile app)?

Using Mobile Device Type as illustrated above allows you to see how people move between mobile device types and desktop device types. However you may want to distinguish desktop browsers from mobile browsers. One way to do this is to create an eVar that records whether the experience occurred on a desktop browser, mobile browser, or mobile app. Then create a Flow diagram as described above, using your "experience" eVar rather than the Mobile Device Type dimension. This provides a slightly different view on cross-device behavior.

## How far back does CDA stitch visitors?

CDA's cross-device stitching occurs in two concurrent processes. 

* The first process is called "live stitching", which occurs as the data streams into Adobe Analytics. During live stitching CDA does the best it can to restate the data at a person level. However, if the person is unknown at the time of live stitching then CDA falls back to the visitor ID to represent the person.

* The second process is called "replay." During replay, CDA goes backwards in time and restates historical data, where possible, within a specified lookback window. This lookback window is either 1 day or 7 days, depending on how you requested CDA to be configured. During replay, CDA attempts to restate hits where the person was previously unknown.

* **If using a device graph**, Adobe keeps device mappings in the Co-op Graph and Private Graph for approximately 6 months. An ECID that has no activity for more than six months is removed from the graph. Data already stitched in CDA is not affected, but subsequent hits for that ECID are treated as a new person.

## How does CDA handle timestamped hits?

Adobe treats timestamped hits as if they were received at the time of the timestamp, not when Adobe received the hit. Timestamped hits older than 1 month are never stitched since they are outside the range Adobe uses for stitching.

## How does CDA compare to custom visitor IDs?

Using a custom visitor ID is a legacy method to [connect users across devices](/help/implement/js/xdevice-visid/xdevice-connecting.md). With a custom visitor ID, you use the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable to explicitly set the ID that is used for visitor logic. The `visitorID` variable overrides any cookie-based IDs that are present.

Custom visitor IDs have several undesirable side effects that CDA overcomes or minimizes. For example, the custom visitor ID methodology has no [replay](replay.md) capabilities. If a user authenticates in the middle of a visit, the first part of the visit associates with a different visitor ID than the latter part of the visit. The separate visitor IDs results in visit and visitor inflation. CDA restates historical data so unaunthenticated hits belong to the correct person.

## Can I upgrade from Custom Visitor ID to CDA?

Customers already using Custom Visitor ID can upgrade to CDA without any implementation changes. The `visitorID` variable is still used in the source report suite. However, CDA ignores the `visitorID` variable in the virtual report suite if a user authenticates.

## How does the device graph handle shared devices?

In some situations it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

* **If using a device graph**, the ability to handle shared devices is limited. The device graph uses an algorithm to determine ownership of a "cluster", and can change each time that cluster is published. Users of the shared device are subject to which cluster they belong to.
* **If using field-based stitching**, the prop or eVar you choose to help identify logged in users overrides other identifiers. Shared devices are considered separate people, even if they originate from the same device.

## How does CDA handle situations where a single person has MANY devices/ECIDs?

In some situations, an individual user can associate with a large number of ECIDs. This can occur if the individual uses a lot of browsers or apps, and can be exacerbated if they frequently clear cookies or use the browser's private or incognito browsing mode.

* **If using a device graph**, CDA caps the number of ECIDs that ties to a given user ID to 50. If a user ID associates with too many ECIDs, the device graph assumes that the user ID is invalid and removes the cluster associated with that user ID. The user ID is then added to a blocklist to prevent it from being added to any clusters in the future. The result in reporting is that user ID is not stitched across devices.
* **If using field-based stitching**, the number of devices is irrelevant in favor of the prop/eVar you choose to help identify logged in users. A single user can belong to any number of devices without impacting CDA's ability to stitch across devices.

## What is the difference between the People metric in CDA and the Unique Visitors metric outside of CDA?

The [People](/help/components/metrics/people.md) metric is similar to the [Unique Visitors](/help/components/metrics/unique-visitors.md) metric in that it reports on the number of unique individuals. However, when using Cross-Device Analytics, unique visitors are combined when they are otherwise recorded as two separate unique visitors outside of CDA. The 'People' metric replaces the 'Unique Visitors' metric when Cross-Device Analytics is enabled. A new metric, [Unique Devices](/help/components/metrics/unique-devices.md), is available that is approximately equal to Unique Visitors outside of Cross-Device Analytics.

## What is the difference between the 'Unique Devices' metric in CDA and the 'Unique Visitors' metric outside of CDA?

These two metrics are roughly equivalent to each other.

## Can I include CDA metrics using the 2.0 API?

Yes. Analysis Workspace uses the 2.0 API to request data from Adobe's servers, and you can view API calls Adobe uses to make your own reports:

1. While logged in to Analysis Workspace, go to [!UICONTROL Help] > [!UICONTROL Enable debugger].
2. Click the debug icon in the desired panel, then select the desired visualization and time of the request.
3. Locate the JSON request, which you can use in your API call to Adobe.

## Cross-Device Analytics can stitch unique visitors together. Can it stitch visits together?

Yes. If an individual sends hits from two separate devices within your virtual report suite's visit timeout (30 minutes by default), they are stitched into the same visit.

## What is the ultimate visitor ID that CDA uses? Can I export it out of Adobe Analytics?

* **If using a device graph**, a custom ID based on their cluster is the primary identifier.
* **If using field-based stitching**, a custom ID based on the prop/eVar you choose is the primary identifier.

Both of these identifiers are calculated by Adobe at the time the report is run, also known as [Report-time processing](../vrs/vrs-report-time-processing.md). The nature of Report-time processing means that it is not compatible with Data Warehouse, data feeds, or other export features that Adobe offers.

## How can I move from the device graph to field-based stitching, or vice versa?

Switching from device graph to field-based stitching or vice versa can be requested via Customer Care. However, making such a switch can take a couple of weeks or more to complete and *historical stitched data from the previous method is lost.*

## How does Adobe handle unique limits for an eVar used in field-based stitching?

CDA pulls eVar dimension items before they are optimized for reporting. You do not need to worry about unique limits for the purposes of CDA. However, if you tried using that prop/eVar in a Workspace project, you can still see the [(Low-traffic)](/help/technotes/low-traffic.md) dimension item.

## How many of my company's report suites can be enabled for CDA?

Multiple report suites may be enabled, however each additional report suite will increase the overall provisioning time if multiple report suites are requested at once. CDA does not merge report suites. Each report suite enabled for CDA needs to be cross-device in nature (containing data from multiple surfaces such as desktop web, mobile web, mobile app, etc.)

## If my Experience Cloud org (a.k.a IMS org) has multiple companies in different regions, can I enable CDA for all of them?

No. For the same org, only one region can have CDA enabled.

## What are the advantages and disadvantages of a 7-day replay versus a 1-day replay?

The advantage of the 7-day replay lookback window is that CDA is able to go back further in time to try to associate previously anonymous events with some person who later logged in within those 7 days. The disadvantages of the 7-day lookback window are 1) replay only runs once per week, and 2) the most recent 7 days are subject to change.

The advantages of using the 1-day replay lookback window are 1) replay runs every day and 2) only yesterday is subject to change. The disadvantage of the 1-day lookback window is that CDA is only able to go back 1 day to try to associate previously anonymous events with a person who logged in yesterday.

## What happens to the stitched data within my CDA virtual report suite(s) if my company decides to downgrade from Analytics Ultimate?

If a customer downgrades from Ultimate, they will no longer have access to stitched data. All previously stitched data will be removed. This means the CDA virtual report suites will now reflect no cross-device stitching. Data will look similar to the original unstitched report suite.

## Why is the total number of hits different between my source report suite and CDA virtual report suite?

CDA uses a complex parallel processing pipeline, with multiple dependent components. A data mismatch of approximately 1% for the total number of hits between the original report suite and the CDA virtual report suite is expected. It has minimal impact on the cross-device capabilities.

## Why is the "Identified People" metric inflated?

If the count is slightly higher than expected, an eVar value can belong to more than one identified person due to [hash collisions](/help/implementation/validate/hash-collisions). If the count is much higher than expected, contact Customer Care for additional troubleshooting steps.
