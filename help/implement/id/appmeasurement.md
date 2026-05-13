---
title: Visitor identification using AppMeasurement
description: Correctly identify visitors when implementing Adobe Analytics using AppMeasurement.
exl-id: 38797ca5-dc53-431e-95df-3c9e68aead94
TQID: https://experienceleague.adobe.com/vWLzF0HXreytCKr01H4-gKzNlO36ySHA2vbcHvT3cIw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Visitor identification using AppMeasurement

AppMeasurement is Adobe Analytics' legacy JavaScript library for data collection. While AppMeasurement by itself offers a native way to identify visitors, many modern browsers reject the third-party cookies that it attempts to set. Adobe strongly recommends using the Adobe Experience Cloud Visitor ID Service in all implementations to conform to modern browser privacy standards. All versions of AppMeasurement come bundled with `VisitorAPI.js`, the JavaScript library used to implement the Visitor ID Service.

## Identifying visitors using the Visitor ID Service (recommended)

Ensure that you are prepared with the following:

* Download the [Latest version of AppMeasurement](https://github.com/adobe/appmeasurement). The downloaded library includes both `AppMeasurement.js` and `VisitorAPI.js`.
* A development [Report suite ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
* The desired edge domain for [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Your IMS org ID:
  1. Log in to [experience.adobe.com](https://experience.adobe.com) using your Adobe ID credentials.
  1. Anywhere in the Experience Cloud interface, press `[Cmd]` + `[I]` (iOS) or `[Ctrl]` + `[I]` (Windows).
  1. A **[!UICONTROL User data debugger]** appears. Select the **[!UICONTROL Assigned orgs]** tab.
  1. Expand the desired IMS organization.
  1. Locate the **[!UICONTROL ID]** field.

Once you have the above resources, the following basic example page contains the minimum required calls to send data to Adobe Analytics:

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>You can track if a hit uses the Visitor ID service by assigning the presence of `Visitor` to a custom variable in [`doPlugins`](/help/implement/vars/functions/doplugins.md):
>
>```js
>s.doPlugins = function() {
>  s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identifying visitors using the `s_vi` cookie (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

If your organization does not use the Visitor ID Service, AppMeasurement uses its own form of visitor identification. When a visitor arrives to your site for the first time, the library checks for a [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. This cookie is set at the domain matching [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (for HTTPS) or [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (for HTTP).

* If you participate in the [Managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), your tracking server would typically be a first-party domain, making `s_vi` cookies first-party.
* If you do not participate in the managed certificate program, tracking server is typically a subdomain of `adobedc.net`, `omtrdc.net`, or `2o7.net`, making the `s_vi` cookie a third-party cookie. Due to modern browser privacy standards, third-party cookies are rejected by most browsers. Once rejected, AppMeasurement attempts to set a first-party fallback cookie (`fid`) instead.

If you correctly set `trackingServerSecure`, then no further visitor identification measures are required.

## Identifying visitors using `visitorID` (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

Using the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable allows your organization complete independent control identifying visitors. If you use `visitorID`, note the following limitations:

* Every hit must contain the same `visitorID` value to be counted as a single visitor.
  * Any hits that omit `visitorID` automatically attempt to use another visitor identification method, treating them as a separate visitor.
  * Any hits that contain a different `visitorID` value from a previous hit are treated as a separate visitor.
  * Adobe does not offer a way to stitch hits using different visitor IDs together in Adobe Analytics.
* Shared audiences, Analytics for Target, and Customer attributes are not supported with visitors identified using `visitorID`.

See [`visitorID`](/help/implement/vars/config-vars/visitorid.md) for implementation instructions using this variable.
