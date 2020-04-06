---
description: Adobe uses a cookie to track unique browsers/devices.
keywords: Analytics Implementation
subtopic: Visitors
title: Identify unique visitors
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
---

# Identify unique visitors

Adobe uses a cookie to track unique browsers/devices.

## Analytics Visitor ID Order {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics provides several mechanisms to identify visitors. The following table lists the different ways a visitor can be identified in Analytics (in order of preference): 

|  Order Used  | Query Parameter (collection method)  | Present When  |
|---|---|---|
|   1 | vid (s.visitorID) | s.visitorID is set  |
|   2 | aid (s_vi cookie)  | Visitor had an existing s_vi cookie before you deployed the Visitor ID service, or you have a visitor ID grace period configured.  |
|   3 | mid (AMCV_ cookie set by Experience Cloud Visitor ID service)  | Visitor's browser accepts cookies (first-party)  |
|   4 | fid (fallback cookie) | Visitor's browser accepts cookies (first-party)  |
|   5 | IP Address, User Agent, Gateway IP Address | Visitor's browser does not accept cookies.  |

In many scenarios you might see 2 or 3 different IDs on a call, but Analytics will use the first ID present from the previous table as the official visitor ID. For example, if you are setting a custom visitor ID (included in the "vid" query parameter), that ID will be used before other IDs that might be present on that same hit.

>[!NOTE] Each Analytics visitor ID is associated with a visitor profile on Adobe servers. Visitor profiles are deleted after at least 13 months of inactivity regardless of any visitor ID cookie expiration.

## Custom Visitor ID

You can implement a custom method to identify visitors by setting the s.visitorID variable.

A custom Visitor ID can be used on sites where you have unique way to identify visitors. An example of this is an ID generated when a user logs in to web site using a user name and password.

Should you have the ability to derive and manage the [!UICONTROL visitor IDs] of your users, you can use the following methods to set the ID: 

|  Method  | Description  |
|---|---|
|  [s.visitorID](../implement/vars/config-vars/visitorid.md) variable  | If JavaScript is used on the browser, or if you are using any other AppMeasurement library, you can set the visitor ID in a data collection variable.  |
|  Query string parameter on the image request  | This lets you pass the [!UICONTROL visitor ID] to Adobe via the [!UICONTROL vid query string] parameter on a hard-coded image request.  |
|  Data Insertion API  | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers.  |
|  URL re-writing and VISTA  | Some deployment architectures provide support for using URL re-writing to maintain session state when a cookie cannot be set. In such cases, Adobe engineering services can implement a [!DNL VISTA] rule that would look for the session value in the URL of the page, then format and place into the [!UICONTROL visid] values.  |
>[!CAUTION]
>**Custom Visitor IDs must be sufficiently granular/unique**: An invalid implementation of custom Visitor IDs can lead to incorrect data and poor reporting performance. If the custom Visitor ID is not unique or granular enough, or is incorrectly set to a common default value such as the string "NULL", or "0", the hits from many different visitors will be seen by Adobe Analytics as a single visitor. This situation results in incorrect data, with visitor counts being too low and segments not working correctly for that visitor. An insufficiently granular custom Visitor ID also prevents the data from being properly spread across nodes in the Analytics reporting cluster. In this situation, one node becomes overloaded and cannot process report requests in a timely fashion. Eventually all reporting for the report suite will fail. <br>Poorly implemented custom Visitor IDs might not immediately impact reporting performance because Analytics can often handle several months' worth of unbalanced data; however, over time a poorly implemented custom Visitor ID value can become problematic to the point of requiring Analytics to disable processing for affected report suites.</br><br>Implementers should follow the guideline that a single custom Visitor ID value should never be credited for more than 1% of your report suite's traffic. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>

## Analytics Visitor ID

When a user visits your site, a persistent cookie is set by the Adobe web server by including it in the HTTP response to the browser. This cookie is set on the specified data collection domain.

When a request is sent to the Adobe data collection server, the header is checked for the visitor ID cookie ( `s_vi`). If this cookie is in the request, it is used to identify the visitor. If the cookie is not in the request, the server generates a unique visitor ID, sets it as a cookie in the HTTP response header, and sends it back with the request. The cookie is stored in the browser and is sent back to the data collection server during subsequent visits the site, which enables the visitor to be identified across visits.

### Third-Party Cookies and CNAME records {#section_61BA46E131004BB2B75929C1E1C93139}

Some browsers, such as Apple Safari, no longer store cookies that are set in the HTTP header from domains that do not match the domain of the current website (this is a cookie used in a third-party context, or a third-party cookie). For example, if you are on `mysite.com` and your data collection server is `mysite.omtrdc.net`, the cookie that is returned in the HTTP header from `mysite.omtrdc.net` might be rejected by the browser.

To avoid this, many customers have implemented CNAME records for their data collection servers as part of a [first-party cookie implementation](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). If a CNAME record is configured to map a hostname on the customer's domain to the data collection server (for example, mapping `metrics.mysite.com` to `mysite.omtrdc.net`), the visitor ID cookie is stored since the data collection domain now matches the domain of the website. This increases the likelihood that the visitor ID cookie will be stored, but it introduces some overhead as you need to configure CNAME records and maintain SSL certificates for data collection servers.

### Cookies on Mobile Devices {#section_7D05AE259E024F73A95C48BD1E419851}

When mobile devices are tracked using cookies, there are some settings you can use to modify how measurement occurs. Cookie default lifetime is 5 years, but you can use the CL query param variable ( `s.cookieLifetime`) to change this default. To set the cookie location for cname implementations, use the CDP query string `s.cookieDomainPeriods`. The default is 2 if no value is specified. and the default location is domain.com. For implementations that do not use CNAME, the visitor ID cookie location is at the 207.net domain.

## Identity Service

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

See [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) for product documentation about this service.

## Identify mobile devices

Most mobile devices accept browser cookies. However, in cases when devices do not accept cookies, another method is used to uniquely identify wireless devices.

Adobe has identified a number of HTTP subscriber ID headers that uniquely identify a majority of mobile devices. Those headers often include the device phone number (or a hashed version of the number), or other identifiers. The majority of current devices have one or more of the headers that uniquely identify the device, and all Adobe data collection servers automatically use those headers in place of a Visitor ID.

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

### Subscriber ID Headers {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

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

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## Fallback ID methods

If other visitor ID methods fail, Adobe sets a fallback cookie or uses a combination of IP address and user agent to identify the visitor.

### Fallback Visitor Identification Method {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). Previously, if a cookie could not be set, visitors were identified using a combination of the IP address and user agent string during data collection.

With this update, if the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2 year expiration and is used as the fallback identification method going forward. This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

Visits total includes all visitors that are identified by the `s_vi` cookie or by using a fallback method.

### IP Address, User Agent, Gateway IP Address {#section_104819D74C594ECE879144FCC5DEF4BF}

. If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.
