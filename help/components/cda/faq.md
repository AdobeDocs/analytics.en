---
title: Cross-Device Analytics FAQ
description: Frequently asked questions for Cross-Device Analytics
---

# Frequently asked questions

**How can I use CDA to see how people move from one device type to another?**

You can use a Flow visualization with the Mobile Device Type dimension.

1. Log in to Adobe Analytics and create a new blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Mobile Device Type' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

**Can I see how people move between different user experiences (e.g. desktop browser vs. mobile browser vs. mobile app)?**

Using Mobile Device Type as illustrated above allows you to see how people move between mobile device types and desktop device types. However you may want to distinguish desktop browsers from mobile browsers. One way to do this is to create an eVar that records whether the experience occurred on a desktop browser, mobile browser, or mobile app. Then create a Flow diagram as described above, using your "experience" eVar rather than the Mobile Device Type dimension. This provides a slightly different view on cross-device behavior.

**How far back does CDA stitch visitors?**

* Adobe keeps device stitching data for approximately 30 days. If a device is intitially not identified by the Co-op Graph or Private graph, but is later identified within 30 days, CDA goes back and restates that device as belonging to identified person up to 30 days in the past. If some of a user's unidentified behavior falls outside the 30-day lookback window, that portion of the user's journey is not stitched.
* Adobe keeps device mappings in the Co-op Graph and Private Graph for approximately 6 months. An ECID that has no activity for more than six months is removed from the graph. Data already stitched in CDA is not affected, but subsequent hits for that ECID are treated as a new individual.

**How does CDA handle timestamped hits?**

Adobe treats timestamped hits as if they were received at the time of the timestamp, not when Adobe received the hit. Timestamped hits older than 1 month cannot be stitched, since they are considered outside the range Adobe keeps data used for stitching.

**How does CDA compare to custom visitor IDs?**

[Custom Visitor ID](/help/implement/vars/config-vars/visitorid.md) is a legacy method to [connect users across devices](/help/implement/js/xdevice-visid/xdevice-connecting.md). With a custom visitor ID, you use the `s.visitorID` variable to explicitly set the ID that is used for visitor logic. The `s.visitorID` variable overrides any cookie-based IDs that are present.

Custom visitor IDs have several undesirable side effects that CDA overcomes or minimizes. For example, the custom visitor ID methodology has no lookback capabilities. If a user authenticates in the middle of a visit, the first part of the visit associates with a different visitor ID than the latter part of the visit. The separate visitor IDs results in visit and visitor inflation. CDA's 30-day lookback window allows it to go backwards in time to restate previous behavior as belonging to the same person, bringing unauthenticated cross-device behavior together with authenticated cross-device behavior with zero or minimal inflation.

**Can I upgrade from Custom Visitor ID to CDA?**

Customers already using Custom Visitor ID can upgrade to CDA. The `s.visitorID` still overrides the underlying cookie-based IDs in the base report suite. However, within the virtual report suite, CDA ignores `s.visitorID` for devices identified by the device graph.

**How does the device graph handle shared devices?**

In some situations it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet. In these cases, the ID syncs to the device graph from these shared devices indicates that multiple users associate with that device over time. The device graph (whether Co-op or Private Graph) does not link the ECID on that device to any one of these users. Instead, the graph links the ECID to a "cluster" that includes all of the associated users. The graph tries to keep this cluster as stable as possible, rather than continually switching the ECID between clusters over time. As a result, CDA cannot distinguish between individual users on a shared device. All users of the shared device are considered a single "person" within CDA.

**How does the device graph handle situations where a single person has MANY devices/ECIDs?**

In some situations, an individual user can associate with a large number of ECIDs. This can occur if the individual uses a lot of browsers or apps, and can be exacerbated if they frequently clear cookies or use the browser's private or incognito browsing mode. The device graph caps the number of ECIDs that ties to a given user ID to 200. If a user ID associates with too many ECIDs, the device graph assumes the user ID is invalid and removes the cluster associated with that user ID. The user ID is then added to a blocklist to prevent it from becoming reclustered in the future. The result in CDA is that user ID's behavior is not stitched across devices.

**What is the difference between the 'People' metric in CDA and the 'Unique Visitors' metric outside of CDA?**

The 'People' metric is similar to the 'Unique Visitors' metric in that it reports on the number of unique individuals. However, when using Cross-Device Analytics, unique visitors are combined when they are otherwise recorded as two separate unique visitors outside of CDA. The 'People' metric replaces the 'Unique Visitors' metric when Cross-device Analytics is enabled.

**What is the difference between the 'Unique Devices' metric in CDA and the 'Unique Visitors' metric outside of CDA?**

These two metrics are roughly equivalent to each other.

**Can I include CDA metrics using the 2.0 API?**

Yes. Analysis Workspace uses the 2.0 API to request data from Adobe's servers, and you can view API calls Adobe uses to make your own reports:

1. While logged in to Analysis Workspace, open your browser's developer tools (F12 for most browsers).
1. In the browser console, type `adobeTools.showDebugger()`. The page reloads with debug icons in the top-right corner of each panel.
1. Click the debug icon in the desired panel, then select the desired visualization and time of the request.
1. Locate the JSON request, which you can use in your API call to Adobe.

**Cross-Device Analytics can stitch unique visitors together. Can it stich visits together?**

Yes. If an individual sends hits from two separate devices within your virtual report suite's visit timeout (30 minutes by default), they are stitched into the same visit.

**What is the ultimate visitor ID that CDA uses? Can I export it out of Adobe Analytics?**

Cross-Device Analytics calculates stitched data using a "cluster ID". This identifier is calculated by Adobe at the time the report is run, also known as Report-time processing. The nature of Report-time processing means that is not compatible with Data Warehouse, data feeds, or other export features Adobe offers.

**How can I move from device graph to field-based stitching?**

If you would like to switch to field-based stitching, you can do so by configuring the virtual report suite. Historical stitched data from the previous method is lost.
