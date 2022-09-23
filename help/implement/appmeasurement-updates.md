---
title: AppMeasurement for JavaScript release notes
description: Cumulative release notes for AppMeasurement for JavaScript.
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
---
# AppMeasurement for JavaScript release notes

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

You can download the latest version of AppMeasurement in the [Code Manager](/help/admin/admin/code-manager-admin.md).

## Version 2.23.0

Release Date: **TBD**

* AppMeasurement now supports the collection of high-entropy user-agent client hints which Chromium browsers (Google Chrome and Microsoft Edge) use to provide device information. You can configure client hints via Tags or use the "collectHighEntropyUserAgentHints" flag. Collection of high-entropy hints is turned off by default. Learn more about User-Agent [client hints](/help/technotes/client-hints.md).


## Version 2.22.4

Release Date: **January 18, 2022**

* The link tracking call `s.tl()` now verifies that the object which is passed to it contains an `href` attribute of type `string`. If it is not a `string`, then it will gracefully ignore the `href` attribute instead of failing. This can occur when passing `svg` objects to the link tracking call.

## Version 2.22.3

Release Date: **October 11, 2021**

* Updated files that referenced Help documentation to point to the current Help locations.

## Version 2.22.2

Release Date: **September 7, 2021**

* This update causes `opt.dmp` and `opt.sell` to always be included when tracking links. Here is a [full list of consent variables](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html).

## Version 2.22.1

Release Date: **August 17, 2021**

* Customers using opt-out may have seen the server-side forwarding opt-out parameters not honored when tracking links. The fixes in this release cause the opt-out flags to be sent if they are present when tracking links.

## Version 2.22.0

Release Date: **August 4, 2020**

* Fix for missing referrer when first hit was not sent due to user's opt-out preferences.

## Version 2.21.0

Release Date: **June 24, 2020**

* Fixed an issue where the Activity Map linkExclusions filter was not always being applied for Firefox.

## Version 2.20.0

Release Date: **March 5, 2020**

* Fixed a security-related issue by updating Internet Explorer detection to suppress JSLint warning.

## Version 2.19.0

Release Date: **February 21, 2020**

* Updated Audience Management module to DIL 9.4. (AN-209341)

## Version 2.18.0

Release Date: **February 13, 2020**

* AppMeasurement can now force cookies to include the Secure attribute by setting the [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) variable. The requirement for this variable is that the entire client website is served securely (HTTPS). (AN-204604)

## Version 2.17.0

Release date: **August 23, 2019**

* Added support for Baidu query string reordering. (AN-182483)
* Fixed an issue that caused stale visitor values in hits that were queued while waiting for opt-in. (AN-184391)

## Version 2.16.0

Release Date: **August 15, 2019**

* Implemented `sendBeacon` support in [!UICONTROL AppMeasurement] for exit links. If a hit uses `sendBeacon` and the page unloads, the request is still completed. This is very useful for exit links because it is more likely that the hit reaches data collection servers. (AN-175142)
* ECID/fid values are now cached on the first hit even though OptIn settings change. (AN-175142)
* Updated  Audience Management Module to DIL 9.3. (AN-182704)
* Exposed switch in `s.ActivityMap.trackScrollReach` to turn scroll reach tracking on or off. (AN-182754)
* Upgraded AppMeasurement to use Visitor ID Service 4.4.0. (AN-182912)

## Version 2.15.0

Release Date: **July 15, 2019**

* Added ActivityMap scroll reach tracking to the Activity Map extension (AN-172949)
* Added DIL 9.2 to AppMeasurement (AN-182472)

## Version 2.14.0

Release Date: **May 21, 2019**

* Fixed issues with management of the state of tracker parameters when multiple hits are pending. (AN-176931, AN-176629, DTM-12758)
* Updated AppMeasurement to include Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Release Date: **April 10, 2019**

* Fix for many reported problems with clearVars. The problem occurs when hits are sent out before the tracker is ready. When the tracker becomes ready, the library can set variables that have already been cleared or changed. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Release Date: **February 22, 2019**

* Updated Audience Management module to DIL 9.1. (AN-175255)
* GTM Security Policy not allowing Activity Map Module. (AN-174679)
* Improved AppMeasurement to honor opt-out when the Identity Service is not approved in opt-in. (AN-175259)

## Version 2.11.0

Release Date: **February 11, 2019**

* Added support for the new Adobe Opt-in services functionality in AppMeasurement. (AN-163546)
* Added support for storing link tracking data on session-storage. (AN-162272)
* Added support for media stream type for Audio Analytics. (AN-173265)

## Version 2.10.0

Release Date: **September 20, 2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] blocks cookie transmissions during POST. (AN-165538)
* Drop support for XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0

Release Date: **May 24, 2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe recommends upgrading to the latest Visitor API version whenever associated code libraries are updated ( [!DNL at.js], [!DNL AppMeasurement.js], and so forth.)

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* Fixed an issue where link tracking cookie keeps getting written after link tracking is turned off. (AN-156332)
* Fixed an issue where `registerPreTrackCallback` and `registerPostTrackCallback` breaks callback function signature when called multiple times. (AN-158566)

## Version 2.8.2

Release Date: **April 12, 2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* Link tracking cookie keeps getting written once link tracking is turned off. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Version 2.8.1

Release Date: **March 29, 2018**

Re-bundle Visitor API 3.1.0 (AN-159524), which includes the hot-fixes: (CORE-11390, CORE-10634)

## Version 2.8.0

Release Date: **March 15, 2018**

Re-bundle Visitor API 3.1.0 (AN-159524), which includes the hot-fixes: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* Refactor building the data collection end point to facilitate sharing. (AN-156647)
* Add request round-trip timing metrics to [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0

Release date: **January 18, 2018**

* Dropping support for IE 6 through 9
* Inclusion of Visitor API v3.0.0
* Inclusion of DIL v7.00

## Version 2.6.0

Release date: **November 9, 2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Version 2.5.0

Release date: **September 21, 2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)
* Inclusion of Visitor API 2.5.0.

## Version 2.4.0

Release date: **August 17, 2017**

* Include dil.js v6.11
* Include Visitor API 2.4.0

## Version 2.3.0

Release date: **July 20, 2017**

* Fixed bug where `s.Util.getQueryParam` captured `#`
* Added v6.10 of `dil.js` (AN-145701)

## Version 2.2.0

Release date: **June 8, 2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusion of version 2.2.0 Visitor API. (AN-144042)

## Version 2.1.0

Release date: **April 20, 2017**

* Included latest version of `dil.js` (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* Re-Included Visitor API 2.1.0. (AN-140873)
* Added `mcorgid` parameter. (AN-139586)
* Added cp (customerPerspective) parameter. (AN-140897)

## Version 2.0.0

Release date: **March 9, 2017**

* Moved to a new build process that requires a version number update to 2.0.0. (AN-137878)
* Moved mboxMCSDID handling into the correct section location where the tracking call is made. (AN-138483)

## Version 1.8.0

Release date: **January 19, 2017**

* Include VisitorAPI 2.0.0
* Re-sequenced function calls and checks so that the SDID is consumed after the abort check has completed. (AN-134364)
* Added `s.registerPreTrackCallback` and `s.registerPostTrackCallback` hooks. (AN-134567)

## Version 1.7.0

Updated: **November 11, 2016**

* Include Visitor API 1.10.1.
* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusion of Visitor API 1.9.0. (AN-132072)
* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411)
* Inclusion of Visitor API 1.8.0 (AN-129887)

## Version 1.6.4

Updated: **August 18, 2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusion of Visitor API 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Experience Cloud ID service.

## Version 1.6.3

Updated: **August 4, 2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Experience Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Experience Cloud ID service, please make sure you are using [!DNL AppMeasurement] code version 1.6.3 or higher.

## Version 1.6.2

Release Date: **July 21, 2016**

* Inclusion of Visitor API 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

## Version 1.6.1

Release date: **June 16, 2016**

* Inclusion of Visitor API 1.5.7.
* Fixed the handling of link click tracking in Firefox that was not firing the complete event.

## Version 1.6

Release Date: **April 21, 2016**

* The [!DNL AppMeasurement] Activity Map module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. Additionally, Activity Map tracking is activated by default. (AN-112689)
* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Version 1.5.4

Release Date: **March 17, 2016**

* Inclusion of Visitor API 1.5.4
* Support for Visitor API 1.5.4+ opt-out

## Version 1.5.3

Release Date: **January 21, 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* Moved the rest of the page URL ("-g") to the end of the tracking request query string. (AN-114647)

## Version 1.5.2

Release Date: **November 5, 2015**

* Inclusion of Visitor API 1.5.3.
* Fixed detection of IE11 for URL Truncation 2047 (AN-114914)

## Version 1.5.1

Release Date: **September 17, 2015**

* Inclusion of Visitor API 1.5.2
* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## Version 1.5

Release Date: **June 18, 2015**

* Support for Visitor API 1.5, which uses the *`getCustomerIDs`* method to gather Customer IDs and authenticated state, and sends the IDs in with data collection requests.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Fixed the known issue described in release 1.4.5.

## Version 1.4.5

Release Date: **May 21, 2015**

* Starting in iOS SDK version 4.5, a new iOS extension lets you collect usage data from your Apple Watch apps, Today widgets, Photo Editing widgets, and all other iOS extension apps. See [iOS extension implementation](https://experienceleague.adobe.com/docs/mobile-services/ios/ios-ext/ios-ext.html) in the Mobile services user guide.
* Starting in Android SDK version 4.5, a new Android extension lets you collect data from your Android wearable app. See [Android wearables](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/android-wearable.html) in the Mobile services user guide.
* Inclusion of Visitor API 1.4.
* Updated AudienceManagement module to use DIL version 6.0.

>[!NOTE]
>
>**Known Issue**: In the Visitor API / [!DNL AppMeasurement] [!DNL Audience Manager] Module integrations, there are two destination publishing iFrame requests made in IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` and  `//fast.<subdomain>.demdex.net/dest4.html`. The correct behavior, as seen in other browsers, is to only load `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4

Release Date: **April 16, 2015**

* You can now include custom context data variables with lifecycle metrics.
* The `trackBeacon` and `clearCurrentBeacon` calls are now available in PhoneGap.
* A minor fix to clear the light server call profile ID after the `trackLight` call.

## Version 1.4.3

Release Date: **February 19, 2015**

* Made all handling of delayed tracking calls consistent, which fixes issues with backed-up variables during the delay, such as the clicked object.
* Changed to not do automatic referrer tracking after the first tracking call so the 2nd, 3rd, etc tracking call (usually link tracking) will not double-count the referrer when *`s.referrer`* was manually set before the first tracking call.
* The distribution zip was updated to include Visitor API 1.3.5.

## Version 1.4.2

Release Date: **January 15, 2015**

* Fixed handling of WebKit prerender handling to prevent tracking of pre-rendered pages that are not viewed.
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Version 1.4.1

Release Date: **September 18, 2014**

* Added a `tagContainerMarker` variable that allows the implementation to specify up to 4 characters that are appended to the version string along with an additional dash character delimiter. This is used by dynamic tag management.

  ```js
  // JavaScript
  s.tagContainerMarker = "D1.0";

  // Data Collection request
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
  ```

  The 4 characters are limited to characters that are allowed in URL file paths, such as alpha-numeric and period.

* On pages that are dual-tagged with H Code, fixed a loop that might occur during automatic link tracking (download and exit) with when forced link tracking is enabled (default in Webkit browsers). Additionally, added a general safeguard around automatic link tracking to prevent similar loops. This safeguard limits automatic link tracking of repeated clicks to the *same* object to once every 10 seconds. This safeguard applies only to automatic link tracking, so manual link tracking (s.tl) calls are not limited. Clicks to different objects are also not impacted by this safeguard and will be tracked.
* Fixed handling of clicked object when a delay is needed.
* Fixed an issue that caused a double page-view count when s.t was called from a link onclick function, if the Visitor API does not have the needed values yet.
* HTTP POST support.

  >[!IMPORTANT]
  >
  >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest Visitor ID Service implementation for the Experience Cloud.

## Version 1.4

Release Date: **August 21, 2014**

* Removed tracking of browser plug-ins (`p` query parameter) as plug-ins are no longer reported in version 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.
* Added support for additional eVars (76 - 250) and events (101-1000).

>[!NOTE]
>
>H-Code does not support the additional eVars and events.

## Version 1.3.2

Release Date: **June 19, 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Support for new features in visitor ID service 1.3.

## Version 1.3.1

Release Date: **May 22, 2014**

* [!DNL AppMeasurement] for [!DNL JavaScript] `s_gi` function was not correctly finding instances created using H code `s_gi`. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Version 1.3

Release Date: **April 17, 2014**

* Support for the [Experience Cloud Visitor ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.2.4

Release Date: **March 13, 2014**

* Bug fixes for heartbeat video.

## Version 1.2.3

Release Date: **February 20, 2014**

* Bug fixes for heartbeat video.

## Version 1.2.2

Release Date: **February 6, 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] customers must also update to version 4.8 of the DIL module.

## Version 1.2.1

Release Date: **November 15, 2013**

* Fixed page events that are used for Heartbeat video measurement.

## Version 1.2

Release Date: **November 14, 2013**

* Added support for [Heartbeat video measurement](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html).
* `VisitorAPI.js` was added to support [Visitor ID Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Version 1.1.1

* Prevented a link tracking call from being sent from Opera browsers for links that start with "opera:" ("opera:" is similar to "about:" and "chrome:" in other browsers).
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Version 1.1

Release Date: **September 18, 2013**

* Fixed support for placing the library and page code in the `head` tag.
* Added missing module `onLoad` support.

## Version 1.0.3

Release Date: **August 15, 2013**

* Added support for deployment through Adobe tag management.
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Version 1.0.2

Release Date: **July 18, 2013**

* The hash/fragment is now ignored by automatic link tracking. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  Now the hash/fragment is ignored so the link is tracked only when the filename ends in an extension that matches.

## Version 1.0.1

Release Date: **May 23, 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. This library provides the same core functionality of [!DNL s_code.js], but is lighter and faster for use on both mobile and desktop sites.

* 3-7x faster than the H.25 code.
* Only 21k uncompressed and 8k gzipped (H.25 code is 33k uncompressed and 13k gzipped).
* Native support to get query parameters, read and write cookies, and perform advanced link tracking.
* Small and fast enough to be used with mobile sites, and robust enough to be used on the full desktop web, allowing you to leverage a single library across all web environments.
