---
title: Visitor identification using AppMeasurement
description: Correctly identify visitors when implementing Adobe Analytics using AppMeasurement.
---
# Visitor identification using AppMeasurement

<!-- Intro -->

## Identifying visitors using the Visitor ID service (recommended)

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
