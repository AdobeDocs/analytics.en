---
title: Visitor identification using AppMeasurement
description: Correctly identify visitors when implementing Adobe Analytics using AppMeasurement.
---
# Visitor identification using AppMeasurement

AppMeasurement is Adobe Analytics' legacy JavaScript library for data collection. While AppMeasurement by itself offers a native way to identify visitors, many modern browsers reject the cookies that it attempts to set. Adobe strongly recommends using the Adobe Experience Cloud Visitor ID Service in all implementations to conform to modern browser privacy standards. All versions of AppMeasurement come bundled with `VisitorAPI.js`, the JavaScript library used to implement the Visitor ID Service.

## Identifying visitors using the Visitor ID Service (recommended)

Use this section to create a basic integration between Adobe Analytics and the Visitor ID Service. Ensure that you are prepared with the following:

* Download the [Latest version of AppMeasurement](https://github.com/adobe/appmeasurement). The downloaded library includes both `AppMeasurement.js` and `VisitorAPI.js`.
* A development [Report suite ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md).
* The desired domain for [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Your IMS org ID:
  1. Log in to [experience.adobe.com](https://experience.adobe.com) using your Adobe ID credentials.
  1. Anywhere in the Experience Cloud interface, press `[Cmd]` + `[I]` (iOS) or `[Ctrl]` + `[I]` (Windows).
  1. A **[!UICONTROL User data debugger]** appears. Select the **[!UICONTROL Assigned orgs]** tab.
  1. Expand the desired IMS organization.
  1. Locate the **[!UICONTROL ID]** field.

Once you have the above resources, see the following basic example page containing the minimum required calls to send data to Adobe Analytics:

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
>You can track if a hit uses the Visitor ID service by assigning the presence of `Visitor` to a custom variable:
>
>```js
>s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI Present" : "VisitorAPI Missing";
>```

## Identifying visitors using the `s_vi` cookie (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

If your organization does not use the Visitor ID Service, AppMeasurement uses its own form of visitor identification. When a visitor arrives to your site for the first time, the library checks for a [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) cookie. This cookie is set at the domain matching [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (for HTTPS) or [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (for HTTP).
   * If you participate in the [Managed certificate program](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert), your tracking server would typically be a first-party domain, making `s_vi` cookies first-party.
   * If you do not participate in the Managed certificate program, tracking server is typically a subdomain of `omtrdc.net` or `2o7.net`, making the `s_vi` cookie a third-party cookie. Due to modern browser privacy practices, third-party cookies are rejected by most browsers. Once rejected, AppMeasurement attempts to set a first-party fallback cookie (`fid`) instead.

If you correctly set `trackingServerSecure`, then no further visitor identification measures are required.

## Identifying visitors using `visitorID` (Not recommended)

>[!IMPORTANT]
>
>Adobe advises against using this method to identify visitors.

Using the [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable allows your organization complete independent control identifying visitors. If you use `visitorID`, note the following limitations:

* Every hit must contain the same `visitorID` value to be counted as a single visitor.
  * Any hits that omit `visitorID` automatically attempt to use another visitor identification method, treating them as a separate visitor.
  * Any hits that contain a different `visitorID` value from a previous hit are treated as a separate visitor.
  * Adobe does not offer any way to stitch hits using different visitor IDs together.
* Shared audiences, Analytics for Target, and Customer attributes are not supported with visitors identified using `visitorID`.

See [`visitorID`](/help/implement/vars/config-vars/visitorid.md) for implementation instructions using this variable.
