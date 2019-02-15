---
description: Cumulative release notes for iOS.
seo-description: Cumulative release notes for iOS.
seo-title: iOS
solution: Analytics,Marketing Cloud
subtopic: Release notes
title: iOS
topic: Developer and implementation
uuid: cc98f8f2-f619-4b31-abf9-e43f4deac64f
---

# iOS{#ios}

Cumulative release notes for iOS.

>[!NOTE]
>
>To find the current library version, turn on debug logging.

Mobile library downloads are available on [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) and on [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-ios).

[4.x documentation](https://marketing.adobe.com/resources/help/en_US/mobile/ios/)

[3.x documentation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/)

## Version 4.13.4 {#section_BF05D33CEF6E42358C8089441449449B}

The [!DNL iOS] SDK version 4.13.4 (Feb 16, 2017) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_657D643E874D47C099F2F43519C9C1C7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>In-App Messaging </p> </td> 
   <td colname="2"> <p> Fixed an issue preventing the proper app version to be used when determining an audience. This issue occurred when a user had an app version upgrade without a new Lifecycle launch. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p> Added a three-second delay prior to making API calls for Apple Search Ad data on app installs (as per the recommendation of the documentation). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.3 {#section_39618D2B29F942FCBF37E4F5507AA131}

The [!DNL iOS] SDK version 4.13.3 (Jan 19, 2017) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_341D35BF18714139A95CA5491899185D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>In-App Messaging </p> </td> 
   <td colname="2"> <p> You can now disable fullscreen messages when VoiceOver is running. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> Improved handling of read-only database access. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>General </p> </td> 
   <td colname="2"> <p> Fixed an issue that could sometimes cause a crash when calling a tracking method from the background while using App Groups. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.2 {#section_CB0DFFDB38FE4D14A84423DF40BF8FD3}

The [!DNL iOS] SDK version 4.13.2 (Nov 10, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_AA26B14D271948FFBA44D4D06E3B71AA"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Visitor ID Service </p> </td> 
   <td colname="2"> <p> Added timestamp and Marketing Cloud Organization ID to <span class="codeph"> adobe_mc</span> parameter. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Configuration </p> </td> 
   <td colname="2"> <p> Invalid IDFAs (00000000-0000-0000-0000-000000000000) passed to the SDK via <span class="codeph"> setAdvertisingIdentifier:</span> will be ignored. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Deep Linking </p> </td> 
   <td colname="2"> <p>When calling <span class="codeph"> trackAdobeDeepLink</span>, variables prefixed with "<span class="codeph"> adb</span>" and "<span class="codeph"> ctx</span>" are now handled properly. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p>Data from Apple Search Ads will now be sent along with your acquisition data. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.1 {#section_18C8A7166EFD4E67AC0F7C06DFBBFE6A}

The [!DNL iOS] SDK version 4.13.1 (Oct 20, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_5B67A6B8B79D4783BA8DCDA7C2ACA765"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Acquisition </p> </td> 
   <td colname="2"> <p> The SDK now supports custom acquisition data to be returned appropriately by <span class="codeph"> AdobeDataCallback</span> invocations. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> <p><span class="keyword"> Visitor ID Service</span> parameters are now passed in <span class="keyword"> Target</span> requests via <span class="codeph"> mboxParams</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Bug Fixes**

* Fixed an issue that could cause a crash when trying to sync new ID to the VisitorID service at the same time as sending tracking hits to [!DNL Adobe Analytics]. 
* Fixed an issue that was causing build warnings when targeting [!DNL iOS] versions older than 8.

## Version 4.13.0 {#section_F72A3357994E4887A9F3967F0FBFFCDD}

The [!DNL iOS] SDK version 4.13.0 (Sep 15, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_FD6156E58FF54BA2BEED7398BC780C46"> 
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
 </tbody> 
</table>

## Version 4.12.0 {#section_2AD26AABBB434833AE961C8D71C9AFE8}

The [!DNL iOS] SDK version 4.12.0 (Aug 18, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_CC3CD01203ED4BDA9BC26427E925C70D"> 
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
  <tr rowsep="1"> 
   <td colname="1"> <p>In-App Messaging </p> </td> 
   <td colname="2"> <p>Fixed an issue that could cause a crash when setting the "target" attribute to "_blank" in an HTML tag in a custom full-screen message. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.11.0 {#section_3ABABE0F0B964EB48BD482CCE260A13D}

The [!DNL iOS] SDK version 4.11.0 (June 22, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_14B23402BA3B41238F419CA57341B8F5"> 
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
     <ul id="ul_93CDE46E39C9431DA9104664F175708B"> 
      <li id="li_903FAC68526B4B7CB6555DC577CE493A"><span class="codeph"> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:requestLocationParameters:callback:</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.10.0 {#section_F0D6D7FD89DE4DF5A121B05FA093CC5B}

The [!DNL iOS] SDK version 4.10.0 (May 20, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_AC447B6E4D55489F803923BF5D1D6653"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target methods </p> </td> 
   <td colname="2"> <p>You can now use the following new <span class="keyword"> Target</span> methods: </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><span class="codeph"> targetLoadRequestWithName:defaultContent:profileParameters:orderParameters:mboxParameters:callback:</span> </li> 
      <li id="li_C0FADBB3CEE141AE951CBD49F3A52642"><span class="codeph"> targetThirdPartyID</span> </li> 
      <li id="li_3E1B3725D9EE4ECE9DB0EB1A9E7682A4"><span class="codeph"> targetSetThirdPartyID:</span> </li> 
      <li id="li_659E295610F541819DD7486FC5177012"><span class="codeph"> targetPcID</span> </li> 
      <li id="li_B00ADCF98B6D4694BB7664DB42CDFF99"><span class="codeph"> targetSessionID</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>TVJS methods </p> </td> 
   <td colname="2"> <p>You can now use the following new <span class="keyword"> Target</span> TVJS methods: </p> <p> 
     <ul id="ul_AED76A2B99534CF3A472AC0381B2618C"> 
      <li id="li_AA731652996C4A19A8E02D5D6B8BDC93"><span class="codeph"> targetThirdPartyID</span> </li> 
      <li id="li_744A63A62A8045E49C75F9D7AED5D75E"><span class="codeph"> targetSetThirdPartyID</span> </li> 
      <li id="li_72BC8D96FE0549A695D90B924FA80A02"> <span class="codeph"> targetPcID</span> </li> 
      <li id="li_FB7A9435B9994DB89FA80C2B2218C047"> <span class="codeph"> targetSessionID</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Adobe Target for TVML/TVJS </p> </td> 
   <td colname="2"> <p>You can now use the following property names when configuring your <span class="codeph"> ADBTarget</span> element: </p> <p> 
     <ul id="ul_A0CEE891AE644B47ABD6F7425ACD464D"> 
      <li id="li_2EB0C3CA52014F45BA1EC07703E821B8"><span class="codeph"> id</span> </li> 
      <li id="li_069D996CED534EE88A1EC82684E470D5"><span class="codeph"> total</span> </li> 
      <li id="li_97F290C03FFD46B8A1E78B7BF2021F55"> <span class="codeph"> purchasedProductIds</span> </li> 
      <li id="li_FAAC4BB12DF9491DA21F161711A7707D"> <span class="codeph"> mboxParameters</span> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.9.0 {#section_DA97D7294B214067A4904B9738450759}

The [!DNL iOS] SDK version 4.9.0 (May 5, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_0B3A0F44549C4DA48C7639048C030065"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Deep linking </p> </td> 
   <td colname="2"> <p>You can implement deep linking in your applications to drive users to app or web link destinations. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.6 {#section_0150641B44CF4F6CBE2B21002F8EAB30}

The [!DNL iOS] SDK version 4.8.6 (March 9, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_5175CFFCA30B4DDBACFB23532111CB8A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Track app crashes </p> </td> 
   <td colname="2"> <p>The <span class="keyword"> iOS</span> SDK version 4.8.6 contains critical changes that prevent false crashes from being reported. We highly recommend that you update to version 4.8.6. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.5 {#section_F42EB64F91024748893E89575F2E4487}

The [!DNL iOS] SDK version 4.8.5 (February 18, 2016) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_AB225AF04A374421BDD8A972506ACD06"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Opt-out and privacy settings </p> </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> SDK 4.8.5, privacy settings set via the <span class="codeph"> setPrivacyStatus</span> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span>, and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.0 {#section_2CF142C8C2D24B529559DAF76F851BBF}

The [!DNL iOS] SDK version 4.8.0 (November 2, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_9DB41F070D66498FACF1A9C135603C7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> New Marketing Cloud Visitor ID Service methods </td> 
   <td colname="2"> <p>Added the following new methods: </p> 
    <ul id="ul_55D8F29ADE3746C484FEC7893FA9EF23"> 
     <li id="li_19F8AF546EEB45EBB5849EA6EB3CE6A3"><span class="codeph"> visitorSyncIdentifiers:authenticationState:</span> </li> 
     <li id="li_1AF1CF62B3ED442D81B438ECBF981583"><span class="codeph"> visitorSyncIdentifierWithType:identifier:authenticationState: </span> </li> 
     <li id="li_C116F0DA8E2A449A8B76637961C2100C"><span class="codeph"> visitorGetIDs</span> </li> 
    </ul> <p>Changed the <span class="codeph"> visitorSyncIdentifiers:identifiers</span> method to <span class="codeph"> visitorSyncIdentifiers:</span> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> New TVJS methods </td> 
   <td colname="2"> <p>Added the following new methods: </p> 
    <ul id="ul_4C7F4BB1CF744444ABAA9F13BA98749E"> 
     <li id="li_5DAB089D115843CCA0A53873D6D676F0"><span class="codeph"> visitorSyncIdentifiersAuthenticationState</span> </li> 
     <li id="li_EDE2D1301E8648DB88A18D8C9F6A22C5"><span class="codeph"> visitorSyncIdentifierWithTypeIdentifierAuthenticationState</span> </li> 
     <li id="li_2CCED3C707774597934A2F08BC690B15"><span class="codeph"> visitorGetIDsJs</span> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> New ADBMobile JSON Config variable </td> 
   <td colname="2"> <p>Added the following variable: </p> 
    <ul id="ul_95065BC06FD540D2937D11111799F77F"> 
     <li id="li_7C8C68A41FBA4D098D6803E71D4CCF7A"><span class="codeph"> analyticsForwardingEnabled</span> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.7.0 {#section_B37B1CAF065346E9A2073A06AB7AFEC2}

The [!DNL iOS] SDK version 4.7.0 (October 15, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_3CCA327B859B498D828B2E056A075BEC"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> tvOS Support </td> 
   <td colname="2"> <p>tvOS is supported for Apple TV. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> App Transport Security Support </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> iOS</span> 9, Apple introduced App Transport Security, a set of requirements that conforms to best practices for secure connections. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> PhoneGap</span> Plugin methods </p> </td> 
   <td colname="2"> <p>Added the following new methods: </p> <p><b>Configuration Methods</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Tracking Methods</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">trackPushMessageClickthrough </li> 
     </ul> </p> <p>New Target method: </p> <p> 
     <ul id="ul_E6A481FCD49D4CF48A4B0636312FCD19"> 
      <li id="li_6604FBB05C4E4988A04CB376D6667C79">targetClearCookies </li> 
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
     </ul> </p> <p><b>App Extensions and Apple Watch Methods</b> </p> <p> 
     <ul id="ul_66B1E1AC4A6D4970B0C77A46EA14ABA7"> 
      <li id="li_1EA7A063FED04E0585D463837A7555CE">setAppGroup </li> 
      <li id="li_5869EAB018C94EE4AC28B3EE62D9F0EF">syncSettings </li> 
      <li id="li_983A98CAEBAD404EBCE1D70CB0B52BA3">initializeWatch </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6 {#section_D091872501DA49C1A18CDC33C84B8256}

The [!DNL iOS] SDK version 4.6 (September 17, 2015) includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_084C27B1A75A4A2EB84822242E37ED35"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p> <span class="keyword"> Adobe Mobile Services</span> and the <span class="keyword"> Adobe Mobile</span> SDK allow you to send push messages to <span class="keyword"> Analytics</span> segments. The SDK also allows you to easily report users that have opened your app as a result of opening the push message. </p> </td> 
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
     <ul id="ul_22EF89556F6B481ABE0D1B9C5EE70B55"> 
      <li id="li_C41F6FAC0B334B89B8B5D1A517CA2301"> <span class="codeph"> setPushIdentifier</span> </li> 
      <li id="li_B7893FB0453340EDB4290BC0B47BF096"><span class="codeph"> setAdvertisingIdentifier</span> </li> 
      <li id="li_85EF5F2B8837497B90F782946283622E">The <span class="codeph"> trackPushMessageClickThrough</span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>WatchKit Support for WatchOS 2 </p> </td> 
   <td colname="2"> <p>Added WatchKit support for WatchOS 2. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.5 {#section_53DFAF8CFD614F69B3168014EF84DE9F}

The [!DNL iOS] SDK version 4.5 includes the following changes: 

<table frame="all" colsep="1" rowsep="1" id="table_A69D0B8DA45348B8A5D6A014126F97C2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Feature </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> iOS</span> Extension </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> iOS</span> SDK version 4.5, a new <span class="keyword"> iOS</span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS</span> extension apps. </p> <p>We strongly recommend that you use the <span class="keyword"> iOS</span> SDK rather than using your own wrapper. </p> <p>Apple provides a set of APIs that lets the Watch app communicate with the containing app (sending requests to the containing app and then receiving responses). </p> <p>Although you can send tracking data as a dictionary from the Watch app to the containing app and then call any tracking method on the containing app to send the data, this solution has limitations. </p> <p>In most cases when a user is using the Watch app, the containing app is running in the background and it is only safe to call <span class="codeph"> TrackActionInBackground</span>, <span class="codeph"> TrackLocation</span>, and <span class="codeph"> TrackBeacon</span>. Calling other tracking methods interferes with lifecycle data, so you should use only these three methods to send the data from Watch app. </p> <p>Even if these three tracking methods meet your requirements, we recommend using the <span class="keyword"> iOS</span> SDK because the SDK for watch app includes all <span class="keyword"> Mobile</span> features except in-app messaging. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.4 {#section_0B7A98761BF0400986C368E154A3B00B}

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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>The <span class="codeph"> trackBeacon</span> and <span class="codeph"> clearCurrentBeacon</span> calls are now available in <span class="keyword"> PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.3 {#section_0FD2B2C4F54E4A9E8C6D0CD2F103BB9A}

Release Date: **November 24, 2014**

* New - Adobe Marketing Cloud ID integration 
* Improved debug logs for clarity

## Version 4.2 {#section_806710F7720C410DAB46376C0A7A283E}

Release Date: **October 16, 2014**

* New - In App Messaging Capabilities. 
* New - Location for config file can now be specified during app startup. 
* New - Points of Interest can now be updated automatically without requiring a new config file. 
* New - [!DNL Analytics] calls are now sent as HTTP POST requests. 
* Cleared up log messages, added more verbose logging when debugLogging is enabled. 
* Multiple performance and stability enhancements.

## Version 4.1.3 {#section_8D679B676F604E0B9A64748569185368}

Release Date: **September 18, 2014**

* Resolved potential crash that could occur if Audience Manager Submit Signal call or [!DNL Target] Load Request call failed due to an unknown network error.

## Version 4.1.2 {#section_6128902E5AE142C4A95D2FB3053188F8}

Release Date: **August 5, 2014**

* Resolved deadlock issue that could occur with the specific configuration of privacyStatus:optunknown and offlineEnabled:false

Release Date: **August 4, 2014**

* Resolved issue that could cause Lifecycle hit to not get sent when referrer timeout was >= 5 seconds and offline tracking was disabled.

Release Date: **April 17, 2014**

* Bluetooth beacon tracking. 
* App acquisition analytics. 
* Apps that are timestamp enabled, crash hits are backdated to the correct session. 
* Apps that are timestamp enabled, previous session is sent in a hit that is backdated to the correct session. (no longer previous session) 
* Hit batching.

## Version 4.0.2 {#section_B78AE82CDFAD44DCAC6D61E0B80BF4C8}

Release Date: **February 20, 2014**

* Resolved issue that caused incorrect behavior when the same media item was opened in sequence without closing previous item.

## Version 4.0.1 {#section_A6D017015BC742F69B6EE4A461D00FD7}

Release Date: **January 30, 2014**

* Resolved issue that could cause multiple hits to be sent when database was corrupted. 
* Resolved issue that could cause large session length averages if a device had incorrect time settings.

## Version 3.3.2 {#section_6D12768F20C44BA4A0D1EA607D367147}

Release Date: **January 30, 2014**

* Resolved issue that could cause large session length averages if a device had incorrect time settings.

## Version 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Release Date: **27 September, 2013**

[!DNL iOS] SDK 4.x for Marketing Cloud Solutions is now available providing the following new features:

* Significant performance enhancements. All processing is performed on background threads, the SDK is fully thread safe. 
* Geo-location & points-of-interest 
* Lifetime value 
* Timed events 
* Opt-in/opt-out management 
* Audience Manager Support 
* Lifecycle metrics passed to [!DNL Target] as mbox parameters 
* Standardized on context data and processing rules

## Version 3.3.0 {#section_28FB7CD64D6C49BF93E321587F1E8950}

Release Date: **23 September, 2013**

* Added support for ARM64 and X64 Simulator architectures (iPhone 5s)

## Version 3.2.1 {#section_3E73A76401664C54B32C7F3BE8BE36E3}

Release Date: **16 August, 2013**

* Optimized by removing unused code. 
* Fixed potential crash that could occur when clearVars was used in a threaded scenario.

## Version 3.2 {#section_A51E0EB26EF246DABE27234C77598D99}

Release Date: **6 August, 2013**

* Added support for Adobe Audience Manager. 
* Lifecycle data is now sent with [!DNL Target] Mbox requests when lifecycle tracking is enabled.

## Version 3.1.8 {#section_849BCD1D4379433D874B8A0E0099E2B1}

Release Date: **20 June, 2013**

* Fixed a bug introduced in 3.1.7 that was causing issues with lifecycle on devices below [!DNL iOS] 5.0.

## Version 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Release Date: **23 May, 2013**

* Added code to prevent excessive lifecycle hits from being sent via location notifications and Newsstand notifications that launch an app.

## Version 3.1.6 {#section_4617D7A41D0841BEBD5829001DC74854}

Release Date: **18 April, 2013**

* Fixed an issue that was causing previous session length to sometimes be calculated incorrectly.

## Version 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Release Date: **21 March, 2013**

* `ADMS_Measurement.visitorID` now gets pre-populated with the default value.

## Version 3.1.4 {#section_B04D1A4858A84A19AA65A57609C9F53F}

Release Date: **21 February, 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. The setting still exists to preserve backwards compatibility, but no longer has any effect.

## Version 3.1.3 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Release Date: **November 2012**

* Fixed a potential EXEC_BAD_Access issue when setting the Products variable manually. 
* Fixed a potential invalid selector crash when an mbox timed out. 
* Added ad tracking support to media measurement.

## Version 3.1.2 {#section_25C8A6B67AB9487BA5DEB4DB196AE4BC}

Release Date: **October 2012**

* Added a `lifecycleSessionTimeout` configuration variable that lets you specify the length of time, in seconds, that must elapse between app launches before the launch is considered a new session. 
* Fixed an issue in the media module that caused events set on the measurement object to overwrite events set by the media module. 
* Fixed an issue that caused an exception when allocating an mbox through the [!DNL Target] integration.

## Version 3.1.0 {#section_0F3E939885DE4DF1B7430DF5F5749AD2}

Release Date: **September 2012**

* Added support for armv7s architecture 
* Removed support for armv6 architecture 
* Minimum supported [!DNL iOS] SDK is now 4.3

## Version 3.0.2 {#section_1224693620524D6C8CCAB7707483536E}

Release Date: **August 2012**

* Customers using media monitor delegate will no longer see two close events 
* Resolved an issue where close hits could sometimes cause a loop condition in media monitor

## Version 3.0 {#section_D28F56359EC04EDC8521BE93750AE90D}

Release Date: **July 2012**

Initial release.

**Enhancements**

* Added "Auto-Tracking" functionality 
* Reduced library size to appx. 90k in final build. 
* Added "trackEvents" and "trackAppState" methods 
* Improved context data support and functionality. (Recommend using context data for all information sent) 
* Simplified tracking so a basic tracking implementation can be done in 5 minutes.

**Changes**

* [!DNL AppMeasurement] Class is now ADMS_Measurement 
* ADMS_Measurement now acts as a proper Singleton 
* Changed getters and setters for eVars, props, lists, hiers, pevs 
* All variables passed into "track" calls will only persist for that call.

**Modified the following variables** 

|  Previous (version 2.x)  | Current (version 3.x)  |
|---|---|
|  account  | reportSuiteIDs  |
|  dc  | dataCenter  |
|  pageName  | appState  |
|  contextData  | persistentContextData  |
|  state  | geoState  |
|  zip  | geoZip  |
|  server  | appSection  |
|  debugTracking  | debugLogging  |
|  trackOffline  | offlineTrackingEnabled  |
|  offlineLimit  | offlineHitLimit  |
|  OfflineThrottleDelay  | offlineThrottleDelay  |

**Repurposed the following variables:**

* linkURL (sent with trackLinkURL:) 
* linkName (sent with trackLinkURL:) 
* linkType (sent with trackLinkURL:) 
* lightProfileID (sent with trackLight:) 
* lightStoreForSeconds (sent with trackLight:) 
* lightIncrementBy (sent with trackLight:) 
* trackingServerSecure (trackingServer is used when ssl is on)

**Removed the following variables:**

* timestamp 
* userAgent 
* dynamicVariablePrefix 
* visitorNamespace 
* pageURL 
* pageType 
* referrer 
* linkLeaveQueryString 
* usePlugins 
* useBestPractices (handled by AutoTracking) 
* delegate 
* retrieveLightData 
* deleteLightProfiles 
* retrieveLightProfiles

## Previous iOS Version (2.x) {#section_5F76C3DA854D4BAEA636A68B3811142B}

The following release notes apply to the 2.x version of [!DNL AppMeasurement] for [!DNL iOS]. We recommend customers upgrade to the 3.x version when possible.

## Version 2.1.12 {#section_85C073B86B684D52A14E8038379F56DD}

Release Date: **April 2012**

* Added support for video measurement. 
* Resolved issues regarding linktrackvars and context data. 
* Made several additional performance enhancements.

## Version 2.1.11 {#section_F0AF2D4E5F504D798EEB95BE8FE61B4C}

Release Date: **March 2012**

* Fixed an issue that caused offline tracking to stop sending data in some circumstances.

## Version 2.1.10 {#section_07C24EC83AA94A6AA6AB3DE7E8D6227F}

Release Date: **February 2012**

* Fixed an issue that caused an EXC_BAD_ACCESS exception in some circumstances when multiple threads attempted to simultaneously make a tracking call. 
* Added time stamp to variables used with light tracking calls (trackLight).

## Version 2.1.8 {#section_ACC6974CE3F741E58786CA8048F04521}

Release Date: **January 2012**

* Significantly increased performance of tracking thread. 
* Moved offline hit storage to a location that is not synchronized to iCloud to conform to iCloud best practices. 
* Updated the library to the Apple fat binary format so you no longer need to include the specific library for your build architecture.

## Version 2.1.6 {#section_63B4967C537847C28D33EBB92CC15695}

Release Date: **November 2011**

* Added support for [!DNL iOS] 5. 
* [!DNL AppMeasurement] for [!DNL iOS] was updated to no longer use the deprecated UDID value as the default value for visitorID. If you set a custom visitorID in your application (for example, `s.visitorID = @12345`), then you are unaffected by this change. If you do not set a custom visitorID, instead of using the UDID as the value for visitorID, a random visitorID is generated on initial launch and then stored in a user defaults key. This key is used by [!DNL AppMeasurement] from that point forward. This key is also saved and restored during the standard application backup process. 

* Updated calls from the [!DNL iOS] Best Practices plug-in that are not associated with a page view to send hits using trackLink. This helps prevent these hits from recording page views with the default value of "application name/version" name.

## Version 2.1.3 {#section_E39666D780554B7398900C39C285CDB8}

Release Date: **October 2011**

* Improved delegate handling. This fixes an issue that caused the [!DNL iOS] Best Practices Plug-in to crash when bringing the application out of the background.

## Version 2.1.2 {#section_21014073AF804EFC8231047D8847485C}

Release Date: **September 2011**

* Updated the header to enable use of prop and eVar 51-75.

## Version 2.1.1 {#section_8FB3D7C77C884E2AB982103BF7E3312A}

Release Date: **August 2011**

* Ability to search report suites and metrics when running a report. 
* Support for context data that drives server-side processing rules (v15 only). 
* Support for light server calls (currently in beta).

