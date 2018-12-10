---
description: Cumulative release notes for Legacy JavaScript H code.
seo-description: Cumulative release notes for Legacy JavaScript H code.
seo-title: JavaScript H Code - Legacy
solution: Analytics
subtopic: Release notes
title: JavaScript H Code - Legacy
topic: Developer and implementation
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
index: y
internal: n
snippet: y
---

# JavaScript H Code - Legacy{#javascript-h-code-legacy}

Cumulative release notes for Legacy JavaScript H code.

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

Release Date: **June 16, 2016**

Inclusion of Visitor API 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

Release Date: **May 19, 2016**

Inclusion of Visitor API 1.5.5.

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

Release Date: **November 5, 2015**

* Inclusion of Visitor API 1.5.3.

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

Release Date: **September 17, 2015**

* Inclusion of Visitor API 1.5.2.

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

Release Date: **August 20, 2015**

* Inclusion of Visitor API 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

Release Date: **June 18, 2015**

* Inclusion of Visitor API 1.5.

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

Release Date: **May 21, 2015**

* Inclusion of Visitor API 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

Release Date: **April 16, 2015**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Release Date: **February 19th, 2015**

* Inclusion of Visitor API 1.3.5. 
* Changed to not perform automatic referrer tracking after first tracking call, so the 2nd, 3rd, etc., tracking call (usually link tracking) will not double count the referrer when *`s.referrer`* was manually set before the first tracking call. (AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

Release Date: **January 15, 2015**

* The distribution zip was updated to include Visitor API 1.3.4.

Release Date: **September 18, 2014**

* Added a `tagContainerMarker` variable that allows the implementation to specify up to 4 characters that are appended to the version string along with an additional dash character delimiter. This is used by dynamic tag management.

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

Release Date: **August 21, 2014**

* Internal changes to support upcoming features.

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Release Date: **June 19, 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors. 
* Support for new features in visitor ID service 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Release Date: **June 11, 2014**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Release Date: **May 22, 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). 
* Support for the [Analytics for Target integration](https://marketing.adobe.com/resources/help/en_US/target/a4t/).

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Release Date: **October 17, 2013**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Release Date: **July 18, 2013**

* The hash/fragment is now ignored by automatic link tracking. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

  Now the hash / fragment is ignored so the link is tracked only when the filename ends in an extension that matches.

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Release Date: **April 29, 2013**

* the `useForcedLinkTracking` option that is described in [Manual Link Tracking Using Custom Link Code](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) now applies to Firefox 20+ (previously this applied to WebKit browsers only). 

* Image object ID generation is now unique between instances. This prevents collisions when more than one instance is on the same page.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Release Date: **April 19, 2013**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices. 

* In video auto tracking on Media Player, fixed an issue in scrubbing that caused time played to not be tracked correctly.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Release Date: **February 2013**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`. 

* Refined scope of click events affected by `useForcedLinkTracking`. The automatic forced link tracking applies only to:

    * `<A>` and `<AREA>` tags 
    
    * The tag must have an `HREF` attribute 
    * The `HREF` can't start with `#`, `about:`, or `javascript:` 
    
    * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Release Date: **January 2013**

* Added support to send URLs longer than 255 bytes to support the expansion of the Page URL field in Adobe Data Collection servers. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. This helps prevent long URLs from taking precedence over other data in the case of browser truncation, but still enables capturing of long URLs. 

* Fixed handling URL decoding for strings that are encoded with a mixed use of `escape` and `encodeURIComponent`. 

* Fixed an issue in WebKit browsers where link tracking fails if the first server call on the page times out. 
* Added a new fallback visitor identification method. See [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors). 
* Added a new `abort` flag that can be set inside `doPlugins`. Setting this flag to true causes the [!DNL AppMeasurement] library to not continue with that tracking call. The abort flag is reset with every tracking call, so if a subsequent tracking call also needs to be aborted the flag will need to be set again inside `doPlugins`. 

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

  This lets you centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Release Date: **October 2012**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. Previously this version was limited to 2 characters (for example, 1.8). Support was added for a 3 character version number (for example, 1.8.5). 
* Fixed an issue with [!DNL Tag Manager] that prevented repeated values in Dependant Code blocks from being sent.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

Release Date: **September 2012**

* Forced URL encoding for the following characters: 

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

  This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie. 

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event: 

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Release Date: **July 2012**

Made an update to ensure that link tracking completes successfully on WebKit browsers (Safari and Chrome). After this update, download and exit links that are automatically tracked (determined by `s.trackDownloadLinks` and `s.trackExternalLinks`) are tracked successfully. If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

For example, exit and download links are often tracked using code similar to the following:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

FireFox and Internet Explorer execute the track link call and open the new page. However, WebKit browsers might cancel execution of the track link call when the new page opens. This often prevents track link calls from completing when using WebKit browsers.

To workaround this behavior, H.25 includes an overloaded track link method ( `s.tl`) that forces WebKit browsers to wait for the track link call to complete. This new method executes the track link call and then handles the navigation event, instead of using the default browser action. This overloaded method requires an additional parameter, called `doneAction`, to specify the action to take when the link tracking call completes.

To use this new method, update calls to `s.tl` with an additional `doneAction` parameter, similar to the following:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Passing 'navigate' as the `doneAction` mirrors the default browser behavior and opens the URL specified by the `href` attribute when the tracking call completes.

The following table summarizes the configuration variables and updates made to H.25 to support this functionality. 

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variable </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>This flag is used to disable forced link tracking for WebKit browsers. Forced link tracking is enabled by default for WebKit browsers and is ignored by other browsers. </p> <p> <b>Default Value</b> </p> <p> <span class="codeph"> true </span> </p> <p> <b>Example</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>The maximum number of milliseconds to wait for tracking to finish before performing the <span class="codeph"> doneAction </span> that was passed into <span class="codeph"> s.tl </span>. This value specifies the maximum wait time. If the track link call completes before this timeout the <span class="codeph"> doneAction </span> is executed immediately. If you notice that track link calls are not completing you might need to increase this timeout. </p> <p> <b>Default Value</b> </p> <p>250 </p> <p> <b>Example</b> </p> 
    <code class="syntax javascript">
      s.forcedLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink ( <span class="codeph"> s.tl </span>) </td> 
   <td colname="col2"> <p>Tracks exit, download, and custom links. Provides an optional parameter to specify a navigation action to execute after the track link call completes on WebKit browsers. </p> <p> <b>Syntax</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) 
    </code> <p> <b>doneAction</b>: (optional) Specifies the action to take after the link track call is sent or has timed out (based on the value specified by <span class="codeph"> s.forcedLinkTrackingTimeout </span>). The <span class="codeph"> doneAction </span> can be the string 'navigate', which causes the method to set <span class="codeph"> document.location </span> to the <span class="codeph"> href </span> attribute of <span class="codeph"> linkObject </span>. The <span class="codeph"> doneAction </span> can also be a function allowing for advanced customization. </p> <p>If providing a value for <span class="codeph"> doneAction </span> in an anchor <span class="codeph"> onclick </span> event, you must return <span class="codeph"> false </span> after the <span class="codeph"> s.tl </span> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <span class="codeph"> href </span> attribute, provide a string of 'navigate' as the <span class="codeph"> doneAction </span>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <span class="codeph"> doneAction </span>. </p> <p> <b>Examples</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="#"&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Release Date: **April 2012**

This update is recommended for all customers.

* Made an enhancement to detect when a page is prerendered using Google Chrome Prerender ( [https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. The [!DNL JavaScript] library now waits until the user visits your site before sending server calls for these prerendered pages. 
* Added the `timestamp` variable to the [!DNL JavaScript] library for customers who want to customize timestamp data similar to other [!DNL AppMeasurement] libraries. 

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Release Date: **February 2012**

* Fixed an issue that caused extra data to be included in the image request for customers using Javascript `Object.prototype` overrides. All `Object.prototype` usage is now skipped when handling context data variables. 
* Fixed an issue that caused the `pe` query parameter to be passed twice with the same value in some circumstances. 
* Fix to [!DNL ClickMap] tracking in [!DNL JavaScript] to ignore clicks to the body tag, even when the tag has an `onClick` event handler. 
* Added time stamp to variables used with light tracking calls ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Release Date: **January 2012**

* Updated video tracking with a new method to track complete video views. 
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE. 
* Fixed a bug where context data variables were not included in link server calls, despite being referenced in `linkTrackVars`. Context data variables are used with Processing Rules.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Release Date: **November 2011**

* Updated video tracking to combine hits for segments and milestones that occur at the same time.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Release Date: **November 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Release Date: **November 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Release Date: **October 2011**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. These settings now apply for automatic exit links so that props, eVars, and events are not sent in with the exit link image request.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Release Date: **September 2011**

* Removed border attributes from image tags on mobile devices to comply with Wireless Markup Language (WML) standards. This fixes rendering issues on some mobile devices.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Release Date: **August 2011**

Fixed accuracy of percentage measurements in video tracking.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Release Date: **July 2011**

* Added support for [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Release Date: **June 2011**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements. 
* Referral strings that are over 255 characters are now truncated by shortening the path rather than the query string. This fixes issues were query string parameters were truncated and not collected.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Release Date: **May 2011**

* Fixed an issue that prevented the video tracking (pev3) variable from being sent. 
* Fixed an issue that prevented the `s_gi` call from enabling code to be compatible with both G and H code. When you pass a 1 as the second parameter to this call the code is now configured to be compatible with both versions.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Release Date: **April 2011**

* Support for contextData that drives server-side processing rules (v15 only). 
* Support for light server calls (v15 only). 
* Support for assigning a value other than 1 to a counter event in the events list. 
* Support for new method of tracking video using conversion eVars and events (currently in beta). 
* Removed support for setting Media.trackWhilePlaying to false. It will always be true. 
* Added debugTracking flag to enable logging of requests send to Firebug console just like the other platforms. 
* Make sure "+" is always URL-encoded regardless of browser.
