---
description: Cumulative release notes for AppMeasurement for JavaScript.
seo-description: Cumulative release notes for AppMeasurement for JavaScript.
seo-title: AppMeasurement for JavaScript
solution: Analytics
subtopic: Release notes
title: AppMeasurement for JavaScript
topic: Developer and implementation
uuid: 1440013d-d266-4dce-9807-8b9adac73315
---

# AppMeasurement for JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Reports & Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL Code Manager]**.

## Version 2.12.0

Release Date: **02/22/2019**

* Updated Audience Management module to DIL 9.1. (AN-175255)
* GTM Security Policy not allowing Activity Map Module. (AN-174679)
* Improved AppMeasurement to honor opt-out when the Experience Cloud ID Service is not approved in opt-in. (AN-175259)

## Version 2.11.0

Release Date: **02/11/2019**

* Added support for the new Adobe Opt-in services functionality in AppMeasurement. (AN-163546)
* Added support for storing link tracking data on session-storage. (AN-162272)
* Added support for media stream type for Audio Analytics. (AN-173265)

## Version 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] blocks cookie transmissions during POST. (AN-165538) 
* Drop support for XDomainRequest. (AN-165733) 
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572) 
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Release Date: **05/24/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe recommends upgrading to the latest Visitor API version whenever associated code libraries are updated ( [!DNL at.js], [!DNL AppMeasurement.js], and so forth.)

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483) 
* Fixed an issue where link tracking cookie keeps getting written after link tracking is turned off. (AN-156332) 
* Fixed an issue where `registerPreTrackCallback` and `registerPostTrackCallback` breaks callback function signature when called multiple times. (AN-158566)

## Version 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Release Date: **04/12/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483) 
* Link tracking cookie keeps getting written once link tracking is turned off. (AN-156332) 
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Version 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Release Date: **03/29/2018**

Re-bundle Visitor API 3.1.0 (AN-159524), which includes the hot-fixes: (CORE-11390, CORE-10634)

## Version 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Release Date: **03/15/2018**

Re-bundle Visitor API 3.1.0 (AN-159524), which includes the hot-fixes: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353) 
* Refactor building the data collection end point to facilitate sharing. (AN-156647) 
* Add request round-trip timing metrics to [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Release date: **01/18/2018**

* Dropping support for IE 6 through 9 
* Inclusion of Visitor API v3.0.0 
* Inclusion of DIL v7.00

## Version 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Release date: **11/09/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Version 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Release date: **09/21/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module) 

* Inclusion of Visitor API 2.5.0.

## Version 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Release date: **08/17/2017**

* Include dil.js v6.11 
* Include Visitor API 2.4.0

## Version 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Release date: **07/20/2017**

* Fixed bug where [!DNL s.Util.getQueryParam] was capturing # 
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Version 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Release date: **06/08/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237) 
* Inclusion of version 2.2.0 Visitor API. (AN-144042)

## Version 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Included latest version of [!DNL dil.js] (AN-140396) 
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920) 
* Re-Included Visitor API 2.1.0. (AN-140873) 
* Added `mcorgid` parameter. (AN-139586) 
* Added cp (customerPerspective) parameter. (AN-140897)

## Version 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Release date: **03/09/2017**

* Moved to a new build process that requires a version number update to 2.0.0. (AN-137878) 
* Moved mboxMCSDID handling into the correct section location where the tracking call is made. (AN-138483)

## Version 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

Release date: **01/19/2017**

* Include VisitorAPI 2.0.0 
* Re-sequenced function calls and checks so that the SDID is consumed after the abort check has completed. (AN-134364) 
* Added the following pre- and post-tracking call hooks. (AN-134567)

    * s.registerPreTrackCallback 
    * s.registerPostTrackCallback

  These functions take as parameters: the callback (a function), and the parameters to that function. For example:

  ```
  s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
      console.log("pre track callback"); 
      console.dir(requestUrl); // Request URL 
      console.dir(a); // param1 
      console.dir(b); // param2 
      console.dir(c); // param3 
  }, "param1", "param2", "param3");
  ```

  The callback is invoked with the `requestUrl` and any parameters passed in when the callback is registered. This occurs either before or after the tracking call, depending on which method is used to register the callback. The order in which these callbacks are called is not guaranteed. Callbacks registered in the pre function are invoked after the final tracking URL is created. The post callbacks are called upon a successful tracking call (if the tracking call fails, these functions are not called). Any callback registered with `registerPreTrackCallback` do not affect the tracking call. Also, calling any of the tracking methods in any registered callback is not recommended and could cause an infinite loop.

## Version 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Updated: **11/10/2016**

* Include Visitor API 1.10.1.

## Version 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Updated: **10/20/2016**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065) 
* Inclusion of Visitor API 1.9.0. (AN-132072)

## Version 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Updated: **9/15/2016**

* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411) 

* Inclusion of Visitor API 1.8.0 (AN-129887)

## Version 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Updated: **8/18/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098) 
* Inclusion of Visitor API 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Version 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Updated: **8/4/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Version 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Release Date: **July 21, 2016**

* Inclusion of Visitor API 1.6.0. 
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006) 
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## Version 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Release date: **June 16, 2016**

Inclusion of Visitor API 1.5.7.

## Version 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Release Date: **May 19, 2016**

[!DNL JavaScript] version 1.5.6

* Inclusion of Visitor API 1.5.6 
* Fixed the handling of link click tracking in Firefox that was not firing the complete event.

## Version 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Release Date: **April 21, 2016**

* The [!DNL AppMeasurement] [!DNL Activity Map] module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. Additionally, [!DNL Activity Map] tracking is activated by default. (AN-112689) 

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Version 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Release Date: **March 17, 2016**

* Inclusion of Visitor API 1.5.4 
* Support for Visitor API 1.5.4+ opt-out

## Version 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Release Date: **January 21, 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381) 
* Moved the rest of the page URL ("-g") to the end of the tracking request query string. (AN-114647)

## Version 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Release Date: **November 5, 2015**

* Inclusion of Visitor API 1.5.3. 
* Fixed detection of IE11 for URL Truncation 2047 (AN-114914)

## Version 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Release Date: **September 17, 2015**

* Inclusion of Visitor API 1.5.2

## Version 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Release Date: **August 29, 2015**

* Inclusion of Visitor API 1.5.1.

## Version 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Release Date: **July 16, 2015**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## Version 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Release Date: **June 18, 2015**

* Support for Visitor API 1.5, which uses the *`getCustomerIDs`* method to gather Customer IDs and authenticated state, and sends the IDs in with data collection requests. 
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1) 
* Fixed the known issue described in release 1.4.5.

## Version 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Release Date: **May 21, 2015** 

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> iOS </span> Extension </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external"> iOS Extension Implementation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android </span> Wearable Extension </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external"> Android Wearable Extension </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusion of Visitor API 1.4. 
* Updated AudienceManagement module to use DIL version 6.0.

**Known Issue**

In the Visitor API / [!DNL AppMeasurement] [!DNL Audience Manager] Module integrations, there will be two destination publishing iFrame requests made in IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` and  `//fast.<subdomain>.demdex.net/dest4.html`. The correct behavior, as seen in other browsers, is to only load `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

Release Date: **April 16, 2015** 

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Custom data with lifecycle metrics </p> </td> 
   <td colname="2"> <p>You can now include custom context data variables with lifecycle metrics. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

A minor fix to clear the light-server call profile ID after the `trackLight` call.

## Version 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Release Date: **February 19, 2015**

* Made all handling of delayed tracking calls consistent, which fixes issues with backed-up variables during the delay, such as the clicked object. 
* Changed to not do automatic referrer tracking after the first tracking call so the 2nd, 3rd, etc tracking call (usually link tracking) will not double-count the referrer when *`s.referrer`* was manually set before the first tracking call. 
* The distribution zip was updated to include Visitor API 1.3.5.

## Version 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Release Date: **January 15, 2015**

* Fixed handling of WebKit prerender handling to prevent tracking of pre-rendered pages that are not viewed. 
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Version 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

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
  >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## Version 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Release Date: **August 21, 2014**

* Removed tracking of browser plug-ins ( `p` query parameter) as plug-ins are no longer reported in version 15. 
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Added support for [additional eVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) and events (101-1000). 

>[!NOTE]
>
>H-Code does not support the additional eVars and events.

[!DNL JavaScript]  

## Version 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Release Date: **June 19, 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors. 
* Support for new features in visitor ID service 1.3.

## Version 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Release Date: **May 22, 2014**

* [!DNL AppMeasurement] for [!DNL JavaScript] `s_gi` function was not correctly finding instances created using H code `s_gi`. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Version 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Release Date: **April 17, 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Version 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Release Date: **March 13, 2014**

* Bug fixes for heartbeat video.

## Version 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Release Date: **February 20, 2014**

* Bug fixes for heartbeat video.

## Version 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Release Date: **February 6, 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] customers must also update to version 4.8 of the DIL module.

## Version 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Release Date: **November 15, 2013**

* Fixed page events that are used for [heartbeat video measurement](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Version 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Release Date: **November 14, 2013**

* Added support for [heartbeat video measurement](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/). 
* [!DNL VisitorAPI.js] was added to support [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Version 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Prevented a link tracking call from being sent from Opera browsers for links that start with "opera:" ("opera:" is similar to "about:" and "chrome:" in other browsers). 
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Version 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Release Date: **September 18, 2013**

* Fixed support for placing the library and page code in the `head` tag. 
* Added missing module `onLoad` support.

## Version 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Release Date: **August 15, 2013**

* Added support for deployment through Adobe tag management. 
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Version 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Release Date: **July 18, 2013**

* The hash/fragment is now ignored by automatic link tracking. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  Now the hash/fragment is ignored so the link is tracked only when the filename ends in an extension that matches.

## Version 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Release Date: **May 23, 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. This library provides the same core functionality of [!DNL s_code.js], but is lighter and faster for use on both mobile and desktop sites.

* 3-7x faster than the H.25 code. 
* Only 21k uncompressed and 8k gzipped (H.25 code is 33k uncompressed and 13k gzipped). 
* Native support to get query parameters, read and write cookies, and perform advanced link tracking. 
* Small and fast enough to be used with mobile sites, and robust enough to be used on the full desktop web, allowing you to leverage a single library across all web environments.

See [AppMeasurement for Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) in the [!DNL Analytics] Implementation Guide.

>[!NOTE]
>
>Some plug-ins are not supported in this new version. See [Plug-in Support](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) for details.
