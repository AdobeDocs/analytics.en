---
title: Debugging tools for Analytics implementations
description: Inspect the data your implementation sends to Adobe using Analytics debuggers, browser developer tools, and HTTP debugging proxies.
keywords: packet analyzer, packet monitor, packet sniffer, debugger, charles, NS_BINDING_ABORTED, sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Debugging tools for Analytics implementations

Debugging tools, sometimes called packet analyzers or packet sniffers, let you inspect the data that your implementation sends to Adobe. They can help you confirm that requests fire successfully, inspect the variables and payloads included in those requests, and troubleshoot unexpected implementation behavior.

>[!NOTE]
>
>The tools listed on this page are not comprehensive. They represent tools that Adobe Analytics customers have found useful. Except for Adobe-provided tools, Adobe does not support or troubleshoot these products. Consult the tool's publisher for installation, usage, and support information.

## Choose a debugging tool

The following categories can help you select a tool based on what you want to inspect.

| Tool type | Useful when |
| --- | --- |
| **Analytics and tag debuggers** | You want Analytics variables, tags, data layers, or collection requests interpreted and presented in a human-readable format. |
| **Browser developer tools** | You are debugging a web implementation and want to inspect network requests directly without installing a separate debugging application. |
| **HTTP(S) debugging proxies** | You want to inspect HTTP traffic from browsers, mobile apps, WebViews, APIs, or other clients, or need capabilities beyond browser developer tools. |

## Analytics and tag debuggers

Analytics and tag debuggers recognize analytics technologies and interpret their requests. These tools can make it easier to identify Adobe Analytics variables, Experience Platform Web SDK payloads, tags, and related implementation information without manually decoding network requests.

| Tool | Availability | Useful for | Considerations |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/home)** | Browser extension | Debugging Adobe Experience Platform and CX Enterprise implementations, including Adobe Analytics, tags, data layers, and Experience Platform Web SDK | Adobe-provided tool focused on Adobe technologies |
| **[Omnibug](https://omnibug.io)** | Chromium-based browsers and Firefox | Decoding Adobe Analytics, Experience Platform Web SDK, Adobe tags, and requests from many other analytics and marketing vendors | Useful for implementations containing technologies from multiple vendors |
| **[ObservePoint Debugger](https://www.observepoint.com/solutions/observepoint-debugger/)** | Chrome and Edge | Inspecting and decoding analytics, marketing, and measurement tags, including Adobe Analytics requests | Browser-based debugger; ObservePoint also offers separate automated implementation-validation products |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home)** | Web application in CX Enterprise | Inspecting and validating events from Mobile SDK implementations, and seeing how Edge Network processed events | Adobe-provided tool; connect your app to an Assurance session to view its events |

## Browser developer tools

Every modern browser includes developer tools that can inspect network requests, so you often do not need a separate tool to debug a web implementation. Press **F12** or **Ctrl+Shift+I** (Windows and Linux) or **Cmd+Option+I** (macOS), then select the **Network** tab. In Safari, first enable developer features in Safari's **Advanced** settings.

## HTTP(S) debugging proxies

HTTP debugging proxies intercept HTTP and HTTPS traffic between a client and a server. They are useful when browser developer tools do not provide enough visibility or when the implementation runs outside of a traditional web browser.

HTTPS inspection generally requires configuring the client to trust a certificate supplied by the debugging proxy. Follow your organization's security policies when installing certificates or intercepting encrypted traffic.

| Tool | Useful for |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | Inspecting browser, application, mobile device, and other HTTP(S) traffic |
| **[Fiddler Everywhere](https://www.telerik.com/fiddler/fiddler-everywhere)** | Capturing and inspecting HTTP(S) traffic across applications and devices. Distinct from the older Fiddler Classic product. |
| **[Proxyman](https://proxyman.com/)** | Inspecting and modifying HTTP(S) traffic from browsers, applications, and mobile devices |
| **[HTTP Toolkit](https://httptoolkit.com/)** | Inspecting traffic from applications, APIs, development environments, and mobile devices, with workflows oriented toward application and API debugging |
| **[mitmproxy](https://www.mitmproxy.org/)** | Scriptable HTTP(S) interception, inspection, and modification through command-line and web interfaces. Best suited for users comfortable with command-line workflows. |

## Locate Adobe Analytics requests

For implementations that send data directly to Adobe Analytics, such as AppMeasurement, filter network requests for:

```text
/ss/
```

Adobe Analytics collection requests contain Analytics variables in the request URL or payload. Raw requests use query parameter names rather than variable names; for example, eVar1 appears as `v1` and prop1 appears as `c1`. Analytics debuggers decode these names for you. To decode them yourself, see the [variable reference](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference) in the Data Insertion API documentation.

For the HTTP status codes that Analytics data collection servers return, see [HTTP response codes](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes) in the Data Insertion API documentation.

For implementations that use Adobe Experience Platform Web SDK, filter network requests for:

```text
/ee/
```

Select the request and inspect its payload to view the data sent to Adobe Experience Platform Edge Network. The Web SDK sends data to the Edge Network, which can then forward data to Adobe Analytics and other configured services. Inspecting the client request verifies what the browser sent to the Edge Network; it does not by itself confirm that the data was successfully processed by every downstream service. To see how Edge Network processed an event, use [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/home).

## Aborted requests

When a page navigates away, the browser can cancel requests that are still in progress. Firefox labels these requests `NS_BINDING_ABORTED`; Chrome and Edge label them `(canceled)`. To keep requests visible after navigation, enable **Preserve log** (Chrome and Edge) or **Persist Logs** (Firefox).

A canceled request does not necessarily mean that data was lost. The browser might have sent the full request and stopped waiting only for the response. Browser developer tools usually cannot show the difference, but an HTTP debugging proxy can.

Requests sent with `navigator.sendBeacon()` are not canceled on navigation. AppMeasurement uses `sendBeacon` for exit links and whenever [`useBeacon`](/help/implement/vars/config-vars/usebeacon.md) is enabled. The Web SDK uses it for events sent with [`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading). If link tracking requests are frequently canceled, use these options.
