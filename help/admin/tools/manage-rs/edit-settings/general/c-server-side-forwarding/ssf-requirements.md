---
description: You must meet these CX Enterprise solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.
solution: Analytics
title: Requirements for server-side forwarding
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Requirements for server-side forwarding

You must meet these CX Enterprise solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.

## Solution Requirements

Server-side forwarding works with [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) and [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) and/or [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html).

## Service Requirements

Server-side forwarding requires the [Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). The Identity Service provides a universal ID that identifies site visitors across all the solutions in CX Enterprise. You need to implement the ID service before server-side forwarding will work.

## Code Versions

Server-side forwarding requires version 1.5 (or newer) of the code libraries listed below. As a best practice, we recommending using the latest versions rather than these required minimums.

*   `AppMeasurement.js`
*   `AppMeasurement_Module_AudienceManagement.js`
*   `VistorAPI.js`

### Determine Your Code Library Version

Any tool that monitors the HTTP requests made by a browser can show you the version number for your AppMeasurement and Visitor API code. The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. The following examples show you what the version IDs for look like for `AppMeasurement.js` and `VisitorAPI.js` code.

*   `AppMeasurement.js`: The [Adobe Debugger](/help/implement/validate/debugger.md) returns the AppMeasurement version like this: `Version of Code | JS-1.5.1`. Other tools may use a different label, but the value always follows the pattern `JS-X.X.X`, where `X` is a version number.
*   `VisitorAPI.js`: Look for the `d_visid_ver` parameter. It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. Visitor API code older than version 1.5.2 did not include a version number. You're probably using an older code library (and need to upgrade) if your monitoring results do not return a version number.
