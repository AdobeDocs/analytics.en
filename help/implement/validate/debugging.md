---
title: Debug Analytics data collection
description: Confirm that Adobe Analytics receives the data you expect from AppMeasurement, the Analytics extension, Web SDK, Mobile SDK, and the Data Insertion API.
keywords: debugging, validation, packet analyzer, packet monitor, /b/ss/, Edge Trace, Assurance, hitdebugger, report suite
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Debug Analytics data collection

This article explains what to check when you debug data sent to Adobe Analytics. Find your implementation method in the following table and follow its section. If you are investigating unexpected report data, start with [Compare requests with reports](#reports).

For steps and tools that apply to all Adobe data collection, such as capturing network requests, enabling debug logging, and investigating canceled requests, see [Debugging and troubleshooting data collection](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview).

| Implementation method | Where to see the data that Analytics receives | Guidance |
| --- | --- | --- |
| AppMeasurement or the Analytics tag extension | Requests from the browser directly to Analytics data collection servers | [AppMeasurement](#appmeasurement) |
| Web SDK | Edge Trace, after the Edge Network converts your event into an Analytics hit | [Web SDK](#web-sdk) |
| Mobile SDK | The Analytics Events view in Assurance. If you use the Edge Network or Edge Bridge extension, turn on **[!UICONTROL Analytics Edge View]**. | [Adobe Analytics Events view in Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/adobe-analytics) |
| Data Insertion API | Your server's outgoing requests and their responses | [Troubleshoot Data Insertion API requests](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement and the Analytics extension {#appmeasurement}

### Find the request {#appmeasurement-find}

[Capture network requests](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web) and filter for `/b/ss/`. Tag debuggers such as Adobe Experience Platform Debugger identify and decode these requests for you.

If no `/b/ss/` request appears:

* Check the browser console for JavaScript errors.
* If you use the Analytics tag extension, confirm that the tag embed code is inside the page's `<head>` element and that your library is published to the environment that you are testing. [Tag debug mode](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging) shows whether the rule that sends the hit fired.
* If you host AppMeasurement yourself, open the library's URL directly to confirm that the file loads and contains code.
* Disable browser extensions, such as ad blockers, that can prevent requests from being sent.
* Debugger does not recognize requests sent from within an iframe. Use browser developer tools instead. See [Use AppMeasurement with iFrames](../use-cases/iframe.md).

### Check what Analytics received {#appmeasurement-contents}

* **Report suites**: The path segment after `/b/ss/` lists the report suite IDs that receive the hit. Confirm that they are the report suites that you expect, such as a development report suite on development pages.
* **Variables**: Raw requests use query parameter names rather than variable names; for example, eVar1 appears as `v1` and prop1 appears as `c1`. See the [variable reference](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference). When a request is too long, AppMeasurement sends it with HTTP `POST`, so variables appear in the request body instead of the URL.
* **Hit type**: Requests sent by [`tl()`](../vars/functions/tl-method.md) include the `pe` parameter and do not increment page views. Requests sent by [`t()`](../vars/functions/t-method.md) do not include `pe`.

If values are present but wrong, see [Troubleshoot JavaScript implementation](../js/troubleshooting.md) for common causes, such as quoting, capitalization, and whitespace.

### Check the response {#appmeasurement-response}

A `2xx` response confirms only that the data collection server received the request, not that the hit was recorded. With the default response type, a request can return success even when the hit is dropped. A `302` response on a new visitor's first request is expected. See [HTTP response codes](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes).

AppMeasurement sends exit link requests, and all requests when [`useBeacon`](../vars/config-vars/usebeacon.md) is enabled, with `navigator.sendBeacon()`. Developer tools can label these requests as canceled even when the browser sent them. See [Aborted requests](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests).

## Web SDK {#web-sdk}

### Find the request {#web-sdk-find}

With Web SDK, the browser sends events to the Edge Network instead of directly to Analytics, so you do not see a `/b/ss/` request. [Inspect the Edge Network request](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests) and confirm the following:

* The `configId` parameter matches a datastream that has the [Adobe Analytics service](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#analytics) enabled with the report suites that you expect.
* The payload qualifies as a page view or a link event. Analytics ignores payloads that contain neither page details nor a web interaction type. See [Edge Network event types in Adobe Analytics](../aep-edge/hit-types.md).

### Check what Analytics received {#web-sdk-contents}

Start an [Edge Trace](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace) and reproduce the action. Locate the row that starts with **[!UICONTROL Analytics Automatic Mapping]**, then expand `mappedQueryParams` and the report suite ID beneath it.

* **Variables**: Mapped values use the same query parameter names as AppMeasurement requests, sometimes in shorthand form, such as `gn` for page name and `pl` for products. See [XDM object field mapping](../aep-edge/xdm-var-mapping.md) and [Data object field mapping](../aep-edge/data-var-mapping.md).
* **Context data**: XDM fields that do not map to an Analytics variable appear as context data with the `c.a.x.` prefix. Use [processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) to assign them to variables.
* **Report suites**: If you use report suite overrides, the datastream configuration row in Edge Trace shows the report suites that the Edge Network used.

### Check processing {#web-sdk-processing}

In the Assurance session that Edge Trace opens, search events for `hitdebugger`. These events use the vendor `com.adobe.analytics.hitdebugger`, and their payloads show values after Analytics processing, such as the Experience Cloud ID (`mcvisId`) and `pageName`.

For a guided walkthrough, see [Set up Adobe Analytics with Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics).

## Compare requests with reports {#reports}

A hit that reaches Analytics does not appear in reports immediately, and reported values can differ from the values in the request:

* **Latency**: Complete data typically appears in reports about two hours after collection. Some data, such as timestamped hits, can take longer. See [Data availability and latency](/help/technotes/latency.md).
* **Processing**: Processing rules, VISTA rules, bot rules, and other processing steps can change or exclude values after collection. See [Processing order for data in Adobe Analytics](/help/technotes/processing-order.md). Assurance post-processed data shows the result of processing for an individual hit.
* **Report suite**: Confirm that you are viewing the same report suite that the request or datastream targeted.
* **Unexpected values**: If a dimension shows unexpected spikes or values, see [Hash collisions](hash-collisions.md).

For broader traffic changes, see [Troubleshoot spikes and drops in data](/help/technotes/event/spikes-drops.md).
