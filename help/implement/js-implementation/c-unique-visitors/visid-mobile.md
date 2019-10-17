---
description: Most mobile devices accept browser cookies. However, in cases when devices do not accept cookies, another method is used to uniquely identify wireless devices.
keywords: Analytics Implementation
seo-description: Most mobile devices accept browser cookies. However, in cases when devices do not accept cookies, another method is used to uniquely identify wireless devices.
seo-title: Identify mobile devices
solution: Analytics
title: Identify mobile devices
topic: Developer and implementation
uuid: 22587dd1-cead-485b-a4d8-94dfb7cd9662
---

# Identify mobile devices

Most mobile devices accept browser cookies. However, in cases when devices do not accept cookies, another method is used to uniquely identify wireless devices.

Adobe has identified a number of HTTP [subscriber ID headers](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) that uniquely identify a majority of mobile devices. Those headers often include the device phone number (or a hashed version of the number), or other identifiers. The majority of current devices have one or more of the headers that uniquely identify the device, and all Adobe data collection servers automatically use those headers in place of a Visitor ID.

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). However, if the device is recognized as a mobile device based on the HTTP headers, a '5' is passed in place of the '1', which indicates that a wbmp format image should be returned and that our list of recognized wireless headers (not a cookie) should be used to identify the device.

The following table lists out the order of the ID methods used based on the return image type value ('1' or '5') in the path: 

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> ID method order </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Default: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">Custom visitor ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Subscriber ID Header </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP Address-UserAgent-Gateway IP Address </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Device was identified as a wireless device, or <code> /5/</code> was manually sent in the image request: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">Custom visitor ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Subscriber ID Header </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP Address-User Agent-Gateway IP Address </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

You can also pass a '1' or a '5' in manual image requests, but be aware that these codes are mutually-exclusive, therefore always passing '5' does not leverage a cookie when it is supported. You can incorporate your own mechanism to determine if a device supports cookies, and if so, pass a '1' in the image rather than a '5'. The accuracy improvement in this situation is limited to the number of mobile devices supporting cookies.

## Subscriber ID Headers {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

The subscriber ID method is generally more reliable than a cookie for user identification because of cookie deletion, cookie acceptance issues, and gateway cookie management issues.

You can improve changes of identifying a visitor by being added to the white list for the carrier that your mobile visitors use. To get access to the carrier's visitor ID, contact the carrier to add your domain to their white list. If you are on a carrier's white list, you also have access to subscriber ID headers that you may not otherwise be able to access.

The following list of headers is used to identify wireless devices. The algorithm for processing the headers is to

1. extract the HTTP header key (the name of the header, such as,"X-Up-Calling-Line-ID") 
1. trim out all non alpha (A-Z and a-z) characters 
1. convert the header key to lowercase 
1. compare the end of the key to the ones in the following table to find a match:

|  Header  | Type  | Example  |
|---|---|---|
|  callinglineid  | ID  | X-Up-Calling-Line-ID: 8613802423312  |
|  subno  | ID  | x-up-subno: swm_10448371100_vmag.mycingular.net  |
|  clientid  | ID  | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com  |
|  uid  | ID  | x-jphone-uid: a2V4Uh21XQH9ECNN  |
|  clid  | ID  | X-Hts_clid: 595961714786  |
|  deviceid  | ID  | rim-device-id: 200522ae  |
|  forwardedfor  | ID or IP Address  | X-Forwarded-For: 127.0.0.1  |
|  msisdn  | ID or IP Address  | X-Wap-msisdn: 8032618185  |
|  clientip  | IP Address  | Client-ip: 10.9.41.2  |
|  wapipaddr  | IP Address  | X-WAPIPADDR: 10.48.213.162  |
|  huaweinasip  | IP Address  | x-huawei-NASIP: 211.139.172.70  |
|  userip  | IP Address  | UserIP: 70.214.81.241  |
|  ipaddress  | IP Address  | X-Nokia-ipaddress: 212.97.227.125  |
|  subscriberinfo  | IP Address  | X-SUBSCRIBER-INFO: IP=10.103.132.128  |

For example "callinglineid" would match "X-Up-Calling-Line-ID" and "nokia-callinglineid." The header type tells us what to expect in the header. The order of header priority is listed here (if a "callinglineid" header is present it is used instead of "subno").

You can use [Dynamic Variables](/help/implement/js-implementation/c-variables/dynvars-overview.md) to extract specific values from a header. 
