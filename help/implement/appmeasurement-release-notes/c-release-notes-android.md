---
description: Cumulative release notes for Android mobile library.
seo-description: Cumulative release notes for Android mobile library.
seo-title: Android
solution: Analytics,Marketing Cloud
subtopic: Release notes
title: Android
topic: Developer and implementation
uuid: 32232d28-3459-4f78-bb00-ca3163c63461
index: y
internal: n
snippet: y
---

# Android{#android}

Cumulative release notes for Android mobile library.

>[!NOTE]
>
>To find the current library version, turn on debug logging.

Mobile library downloads are available on [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) and on [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1).

## Version 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

The [!DNL Android] SDK version 4.13.4 (Feb 16, 2017) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> In-App Messaging </p> </td> 
   <td colname="2"> <p> Fixed an issue preventing the proper app version to be used when determining an audience. This issue occurred when a user had an app version upgrade without a new Lifecycle launch. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Lifecycle </p> </td> 
   <td colname="2"> <p> Fixed an issue that could prevent an app version upgrade from being properly reported. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> <p> Fixed a bug that was causing deferred deep links to not be triggered on the first launch. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

The [!DNL Android] SDK version 4.13.3 (Jan 19, 2017) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> In-App Messaging </p> </td> 
   <td colname="2"> <p> Fixed an issue that prevented the display of alert messages with no click-through button. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Improved handling of read-only database access. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Universal Links </p> </td> 
   <td colname="2"> <p> Fixed a bug that was causing deferred deep links attached to acquisition data to fire on successive launches. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

The [!DNL Android] SDK version 4.13.2 (Nov 10, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Visitor ID Service </p> </td> 
   <td colname="2"> <p>Added timestamp and Marketing Cloud Organization ID to <span class="codeph"> adobe_mc</span> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Deep Linking </p> </td> 
   <td colname="2"> <p>When calling <span class="codeph"> trackAdobeDeepLink</span>, variables prefixed with "<span class="codeph"> adb</span>" and "<span class="codeph"> ctx</span>" are now handled properly. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

The [!DNL Android] SDK version 4.13.1 (Oct 20, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> The SDK now supports custom acquisition data to be returned appropriately by <span class="codeph"> AdobeDataCallback</span> invocations. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition </p> </td> 
   <td colname="2"> The SDK now stores Google Play Referrer variables and custom variables and returns them appropriately in <span class="codeph"> AdobeDataCallback</span> invocations. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> Visitor ID Service parameters are now passed in <span class="keyword"> Target</span> requests via <span class="codeph"> mboxParams</span>. </td> 
  </tr> 
 </tbody> 
</table>

**Bug Fixes**

* Fixed a bug where data requests to the phone would sometimes timeout.

## Version 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

The [!DNL Android] SDK version 4.13.0 (Sept 15, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>In-App Messaging </p> </td> 
   <td colname="2"> <p>New feature: Added a new message type that opens a deep link URI. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Tracking Deep Links </p> </td> 
   <td colname="2"> <p>New feature: Added the ability to enable tracking of 3rd party deferred deep links. </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><span class="codeph"> processAdobeDeepLink</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

The [!DNL Android] SDK version 4.12.0 (Aug 18, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Visitor ID Service </p> </td> 
   <td colname="2"> <p> Added new method to append visitor identity to a given URL in order to transfer identity to a web-based implementation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

The [!DNL Android] SDK version 4.11.0 (June 22, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target methods </p> </td> 
   <td colname="2"> <p>You can now use the following new <span class="keyword"> Target</span> method: </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><span class="codeph"> loadRequest</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

The [!DNL Android] SDK version 4.10.0 (May 20, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Target methods </td> 
   <td colname="2"> <p>Added new syntax and example for the <span class="codeph"> loadRequest</span> method. </p> <p>Added the following new <span class="keyword"> Target</span> methods: </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

The [!DNL Android] SDK version 4.9.0 (May 5, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Opt-out and privacy settings </td> 
   <td colname="2"> <p>You can implement deep linking in your applications to drive users to app or web link destinations. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

The [!DNL Android] SDK version 4.8.3 (February 18, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Opt-out and privacy settings </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <span class="codeph"> setPrivacyStatus</span> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

The [!DNL Android] SDK version 4.8.0 (November 2, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> New Marketing Cloud Visitor ID Service methods </td> 
   <td colname="2"> <p>Added the following methods: </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><span class="codeph"> syncIdentifer</span> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><span class="codeph"> syncIdentifiers</span> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><span class="codeph"> getIdentifiers</span> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> New ADBMobile JSON Config variable </td> 
   <td colname="2"> <p>Added the following variable: </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><span class="codeph"> analyticsForwardingEnabled</span> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> PhoneGap</span> Plugin methods </td> 
   <td colname="2"> <p>Added the following new methods </p> <p><b>Configuration Methods</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Target Methods</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
     </ul> </p> <p><b>Acquisition Methods</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Audience Manager Methods</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>Visitor ID Service Methods</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

The [!DNL Android] SDK version 4.6.1 (September 24, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android</span> SDK version 4.6.1 </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

The [!DNL Android] SDK version 4.6 (September 17, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p><span class="keyword"> Adobe Mobile Services</span> and the <span class="keyword"> Adobe Mobile</span> SDK allow you to send push messages to <span class="keyword"> Analytics</span> segments. The SDK also allows you to easily report users that have opened your app as a result of opening the push message. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisition Methods </p> </td> 
   <td colname="2"> <p>Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Postbacks </p> </td> 
   <td colname="2"> <p>Postbacks let you send data collected by the SDK to a separate third-party server. Leveraging the same triggers and traits you use to display an in-app message, you can configure the SDK to send customized data to a third-party destination. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Identifiers </p> </td> 
   <td colname="2"> <p>Added the following new identifiers: </p> <p> 
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><span class="codeph"> setPushIdentifier</span> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <span class="codeph"> submitAdvertisingIdentifierTask</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

The [!DNL Android] SDK version 4.5 includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android</span> Wearable Extension </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

The [!DNL Android] SDK version 4.4 includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>The <span class="codeph"> trackBeacon</span> and <span class="codeph"> clearCurrentBeacon</span> calls are now available in <span class="keyword"> PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

Release Date: **November 24, 2014**

* New - Adobe Marketing Cloud ID integration 
* Improved debug logs for clarity 
* Resolved potential crash when checking for in-app messages

## Version 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

Release Date: **October 16, 2014**

* New - In App Messaging Capabilities. 
* New - Location for config file can now be specified during app startup. 
* New - Points of Interest can now be updated automatically without requiring a new config file. 
* New - [!DNL Analytics] calls are now sent as HTTP POST requests. 
* Resolved issue that could cause app crashes to not be tracked in certain scenarios. 
* Cleared up log messages, added more verbose logging when debugLogging is enabled. 
* Multiple performance and stability enhancements.

## Version 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

Release Date: **August 4, 2014**

* Resolved issue that could cause Lifecycle hit to not get sent when referrer timeout was >= 5 seconds and offline tracking was disabled.

## Version 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

Release Date: **July 17, 2014**

* Added protections around exceptions that occur if the database become corrupted, or could not be created. 
* Added protections for issues that could occur when config cannot be loaded (generally due to a null context). 
* Added protections for exceptions that could occur when updating the context data of a timed action.

## Version 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

Release Date: **April 23, 2014**

* Fixed a potential issue that could occur if referrer tracking is enabled and a tracking call is made prior to lifecycle.

## Version 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

Release Date: **April 17, 2014**

* - New - Bluetooth beacon tracking. 
* - New - Apps that are timestamp enabled, crash hits are backdated to the correct session. 
* - New - Apps that are timestamp enabled, previous session is sent in a hit that is backdated to the correct session. (no longer previous session). 
* - New - Hit batching. 
* - Fixed google play referrer tracking with a configurable timeout to allow for delayed google referrer data. 
* - Resolved StrictMode warnings that could occur in specific scenarios. 
* - Resloved an issue that could very rarely cause the library to lock if certain methods were called in a specific order.

## Version 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

Release Date: **February 24, 2014**

* Resolved issue that could cause extended media time played if stop was called and close was called later with no calls in between. 
* Resolved issue where a media close hit was sent even if the media was not played for any length of time.

## Version 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

Release Date: **February 20, 2014**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## Version 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

Release Date: **January 30, 2014**

* Resolved issue that could cause multiple hits to be sent when database was corrupted. 
* Resolved issue that could cause large session length averages if a device had incorrect time settings.

## Version 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

Release Date: **30 January, 2014**

* Added protections against corrupted databases causing hits to repeat. 
* Added max session length limit to avoid extremely large sessions when device times are incorrect.

## Version 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

Release Date: **14 November, 2013**

* Resolved incorrect formatting of trackLocation data in specific locales.

## Version 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Release Date: **27 September, 2013**

[!DNL Android] SDK 4.x for Marketing Cloud Solutions is now available providing the following new features:

* Significant performance enhancements. All processing is performed on background threads, the SDK is fully thread safe. 
* Geo-location & points-of-interest 
* Lifetime value 
* Timed events 
* Opt-in/opt-out management 
* Audience Manager Support 
* Lifecycle metrics passed to Target as mbox parameters 
* Standardized on context data and processing rules

## Version 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

Release Date: **23 September, 2013**

* Fixed a bug in Audience Manager not allowing null values or keys in parameter.

## Version 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

Release Date: **12 September, 2013**

* Fixed a bug where media events in linkTrackEvents were not added to the request. 
* Fixed a potential exception related to ContextData being modified after being passed into a track call.

## Version 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

Release Date: **16 August, 2013**

* SSL Connections now use strict host validation 
* Fixed bug where hits would rapidly retry for a few seconds when network connection was lost and offlineTracking was disabled.

## Version 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

Release Date: **6 August, 2013**

* Added support for Adobe Audience Manager. 
* Lifecycle data is now sent with Target Mbox requests when lifecycle tracking is enabled. 
* Resolved an issue that could cause SQLite to force close cursors, resulting in unnecessary log entries.

## Version 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

Release Date: **13 June, 2013**

* Updated offline storage to use SQLite. 
* Fixed a bug where offline limit could reset to default (1000). 
* Updated startActivity to now accept an Activity or Application context. 
* Fixed a bug where setting lifcycleSessionTimeout to 0 would result in multiple launch events throughout the app.

## Version 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

Release Date: **18 April, 2013**

* Fixed encoding issue with some UTF8 characters.

## Version 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

Release Date: **18 April, 2013**

* Fixed an issue that was causing previous session length to sometime be calculated incorrectly. 
* New visitor IDs will no longer be based off of deviceID or subscriberID. 
* Fixed a potential crash when encoding special characters in variables.

## Version 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

Release Date: **21 March, 2013**

* Fixed issue where visitorID could not be read without setting it first. 
* Changed naming conventions in some error log messages for clarity. 
* Changed accessibility of multiple base classes to avoid confusion. 
* Multiple performance enhancements

## Version 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

Release Date: **21 February, 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. The setting still exists to preserve backwards compatibility, but no longer has any effect. 
* Fixed potential synchronization issue on offline hit cache. 
* Clarified warning message when setting hierarchical vars over #5. 
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] > 4.0. 
* Multiple performance enhancements. 
* Resolved a potential exception that could be caused by a malformed url.

## Version 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

Release Date: **November 2012**

* Added a `lifecycleSessionTimeout` configuration variable that lets you specify the length of time, in seconds, that must elapse between app launches before the launch is considered a new session. 
* Added ability to set the timeout value for the session length calculation, using a `lifecycleSessionTimeout` configuration setting. 
* Fixed security issues.

## Version 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

Release Date: **October 2012**

* Added support for [Google Play Campaign Tracking](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/index.html?f=referrer).

## Version 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

Release Date: **September 2012**

* Resolved an issue where close hits could sometimes cause a loop condition in media monitor.

## Version 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

Release Date: **August 2012**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## Version 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

Release Date: **July 2012**

Initial release.

## Previous Android Version (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. We recommend customers upgrade to the 3.x version when possible.

## Version 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

Release Date: **March 2012**

* Fixed an issue that caused an exception in some circumstances when passing data using Context Data.

## Version 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

Release Date: **February 2012**

Fixed an issue that caused link tracking calls to double-URL-encode the pev1 - pev3 values.

Added time stamp to variables used with light tracking calls (trackLight).

## Version 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

Release Date: **January 2012**

* Added [!DNL Android] 3.x and 4.x compatibility. 
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## Version 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

Release Date: **June 2011**

* Updated the library to use the device ID for the visitor ID value when no SIM card is inserted in the device. By default the library uses the subscriber ID as the visitor ID which is not present if no SIM card is inserted.

## Version 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

Release Date: **April 2011**

* Support for all tablets including the Xoom. 
* Ability to search report suites and metrics when running a report. 
* Support for contextData that drives server-side processing rules (v15 only). 
* Support for light server calls (currently in beta).
