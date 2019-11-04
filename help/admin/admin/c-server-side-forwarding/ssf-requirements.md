---
description: You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.
seo-description: You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.
seo-title: Requirements for server-side forwarding
solution: Audience Manager
title: Requirements for server-side forwarding
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
---

# Requirements for server-side forwarding

You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.

## Solution Requirements

Server-side forwarding works with [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) and [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) and/or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Service Requirements

Server-side forwarding requires the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). The Identity Service provides a universal ID that identifies site visitors across all the solutions in the Experience Cloud. You need to implement the ID service before server-side forwarding will work.

## Code Versions

Server-side forwarding requires version 1.5 (or newer) of the code libraries listed below. As a best practice, we recommending using the latest versions rather than these required minimums.

*   `AppMeasurement.js`
*   `AppMeasurement_Module_AudienceManagement.js`
*   `VistorAPI.js`

### Determine Your Code Library Version

Any tool that monitors the HTTP requests made by a browser can show you the version number for your AppMeasurement and Visitor API code. The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. The following examples show you what the version IDs for look like for `AppMeasurement.js` and `VisitorAPI.js` code.

*   `AppMeasurement.js`: The [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) returns the AppMeasurement version like this: `Version of Code | JS-1.5.1`. Other tools may use a different label, but the value always follows the pattern `JS-X.X.X`, where `X` is a version number.
*   `VisitorAPI.js`: Look for the `d_visid_ver` parameter. It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. Visitor API code older than version 1.5.2 did not include a version number. You're probably using an older code library (and need to upgrade) if your monitoring results do not return a version number.
