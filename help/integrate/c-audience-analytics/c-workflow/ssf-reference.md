---
description: A comprehensive list and descriptions of the configuration variables, HTTP headers, and data signals in server-side forwarding calls.
seo-description: A comprehensive list and descriptions of the configuration variables, HTTP headers, and data signals in server-side forwarding calls.
seo-title: Server-side forwarding data and code reference
title: Server-side forwarding data and code reference
uuid: aef61544-7b29-40e7-b5a7-a21cd4cff5a9
index: y
internal: n
snippet: y
---

# Server-side forwarding data and code reference

A comprehensive list and descriptions of the configuration variables, HTTP headers, and data signals in server-side forwarding calls.

## Configuration Variables {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). See also [Supported Attributes for DCS API calls](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

|Parameter|Description|
|--- |--- |
|`d_rs`|(Gets set with legacy/tracking-server-based server-side forwarding) <br/>Set to the report suites passed in with the hit to Analytics.|
|`d_dst_filter`|(Gets set with report-suite-based server-side forwarding)  <br/>Set to the report suite IDs passed in with the hit to Analytics.|
|`d_dst`|Set  d_dst=1  <br/>if the request to Analytics is expecting content about the destination to be sent back to the client.|
|`d_mid`|The Experience Cloud ID passed in to Analytics. See Cookies and the Experience Cloud ID Service .|

## HTTP Headers {#section_0549705E76004F9585224AEF872066C0}

These headers are fields contain information like requests for data and responses in an HTTP call.

|HTTP Header|Description|
|--- |--- |
|Host|This is set to the client's specific data collection host name specified in the Analytics host config file. It appears as  host name `.demdex.net` .  See  Understanding Calls to the Demdex Domain .|
|User-Agent|Set to the User-Agent header passed in to Analytics.|
|X-Original-User-Agent|Only set if an alternate user agent was specified by one of these headers:   <br/>`X-Device-User-Agent\`   <br/>`X-Original-User-Agent\`   <br/>`X-OperaMini-Phone-UA\`   <br/>`X-Skyfire-Phone\`   <br/>`X-Bolt-Phone-UA\`|
|X-Forwarded-For|Set to the IP address of the requesting client. Analytics will have already parsed the incoming `X-Forwarded-For`  header and determined the correct IP address to use.|
|Accept-Language|Set to the  Accept-Language  header passed in to Analytics.|
|Referer|Set to the page URL passed in to Analytics or gathered from the  Referer  header passed in to Analytics.|

## Customer-Defined Signals {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_*` identify customer-defined variables. See also [Supported Attributes for DCS API Calls](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.htmld).

<table id="table_D679E65573AA421C9C75E575894D7096"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Signal </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_browserWidth </span> and <span class="codeph"> c_browserHeight </span> </p> </td> 
   <td colname="col2"> <p>Browser window width and height. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_campaign </span> </p> </td> 
   <td colname="col2"> <p>Set by <span class="codeph"> s.campaign </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_channel </span> </p> </td> 
   <td colname="col2"> <p>Set by <span class="codeph"> s.channel </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_clientDateTime </span> </p> </td> 
   <td colname="col2"> <p>Timestamp formatted as <span class="codeph"> <span class="varname"> dd/mm/yyy hh:mm:ss </span> W TZ </span>. </p> <p> <span class="codeph"> TZ </span> is in minutes and matches the return of the <span class="codeph"> Date.getTimezoneOffset </span> method. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_colorDepth </span> </p> </td> 
   <td colname="col2"> <p>Specified as 16- or 32-bit color. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_connectionType </span> </p> </td> 
   <td colname="col2"> <p>Specifies connection type. Options include: </p> <p> 
     <ul id="ul_16EA25B7C49B41E0819BC6BB2D30E674"> 
      <li id="li_57C9D89A446444A5A2115FF7C7EFB82D"> <span class="codeph"> modem </span> </li> 
      <li id="li_A7AB7C5A936848C69269FB017C632CA1"> <span class="codeph"> lan </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_contextData.* </span> </p> </td> 
   <td colname="col2"> <p>Examples: </p> <p> 
     <ul id="ul_9D02AEBC0E5940E998461B91F3743B65"> 
      <li id="li_8F0B73FAC03F43FE9256429E535C8826">AppMeasurement: <span class="codeph"> s.contextData["category"] = "news"; </span> </li> 
      <li id="li_13B95C5EC2D64FF983306DB11EDED2B8">Signal: <span class="codeph"> c_contextData.category=news </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_cookiesEnabled </span> </p> </td> 
   <td colname="col2"> <p>Specifies if cookies can be enabled. Options include: </p> <p> 
     <ul id="ul_76559121B9174ECC9EB15252F6271269"> 
      <li id="li_E961238FE6E043F2A2921CA4A48A7946"> <span class="codeph"> yes </span> </li> 
      <li id="li_667B1110DAFF4A6EBF11D9A25496F249"> <span class="codeph"> no </span> </li> 
      <li id="li_A2006AFB970A407DBA22909E1717D090"> <span class="codeph"> unknown </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_currencyCode </span> </p> </td> 
   <td colname="col2"> <p>Type of currency used for the transaction. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_evar# </span> </p> </td> 
   <td colname="col2"> <p>Custom evars </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_events </span> </p> </td> 
   <td colname="col2"> <p>Set by <span class="codeph"> s.events </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_hier# </span> </p> </td> 
   <td colname="col2"> <p>Custom hierarchy variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_javaEnabled </span> </p> </td> 
   <td colname="col2"> <p>Specifies if Java can be enabled. Options include: </p> <p> 
     <ul id="ul_DB2979181E2A44D18113704004AA8597"> 
      <li id="li_25103160202147A6B1D99EA552F7F31E"> <span class="codeph"> yes </span> </li> 
      <li id="li_BB12D3D2A9434B6A9EF84E79CB5BD5FD"> <span class="codeph"> no </span> </li> 
      <li id="li_91D7DD18F2144415B873347D881520E6"> <span class="codeph"> unknown </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_javaScriptVersion </span> </p> </td> 
   <td colname="col2"> <p>Version of JavaScript supported by a browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_latitude </span> </p> </td> 
   <td colname="col2"> <p>Numeric latitude </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_linkClick </span> </p> </td> 
   <td colname="col2"> <p>Options include: </p> <p> 
     <ul id="ul_F763A31B312A4E388DEBB6C68DAB5CB2"> 
      <li id="li_F07BBFFF1B5740258DAEF5796A93620C"> <span class="codeph"> custom </span> </li> 
      <li id="li_879DAC4786E94098A5771C1F82462168"> <span class="codeph"> download </span> </li> 
      <li id="li_F65276DE55CE4E25831021A4661C771C"> <span class="codeph"> exit </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_linkCustomName </span> </p> </td> 
   <td colname="col2"> <p>The custom name (if any) provided for the link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_linkDownloadURL </span> </p> </td> 
   <td colname="col2"> <p>The URL of download links. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_linkExitURL </span> </p> </td> 
   <td colname="col2"> <p>The exit link URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_list# </span> </p> </td> 
   <td colname="col2"> <p>Custom list variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_longitude </span> </p> </td> 
   <td colname="col2"> <p>Numeric longitude. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_mediaPlayerType </span> </p> </td> 
   <td colname="col2"> <p>For media stream tracking requests. Options include: </p> 
    <ul id="ul_54A6496C33834C06A3F1A049359EAB83"> 
     <li id="li_4F00B2B2D025488DB4D559C32B436E75"> <span class="codeph"> other </span> </li> 
     <li id="li_23B587C42FFF4C12B5921D0493954914"> <span class="codeph"> primetime </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_pageName </span> </p> </td> 
   <td colname="col2"> <p>The page name (if set). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_pageURL </span> </p> </td> 
   <td colname="col2"> <p>The address of the page in the address bar of the browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_products </span> </p> </td> 
   <td colname="col2"> <p>The product string (set by <span class="codeph"> s.products </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_prop </span> </p> </td> 
   <td colname="col2"> <p>Custom props. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_purchaseID </span> </p> </td> 
   <td colname="col2"> <p>A unique ID for the purchase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_referrer </span> </p> </td> 
   <td colname="col2"> <p>The page prior to the current page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_screenResolution </span> </p> </td> 
   <td colname="col2"> <p>Screen width and height (in pixels). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_server </span> </p> </td> 
   <td colname="col2"> <p>Web server name (set by <span class="codeph"> s.server </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_state </span> </p> </td> 
   <td colname="col2"> <p>Geographic region (set by <span class="codeph"> s.state </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_timezone </span> </p> </td> 
   <td colname="col2"> <p>Time offset (in hours). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_transactionID </span> </p> </td> 
   <td colname="col2"> <p>A unique ID for a transaction. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c_zip </span> </p> </td> 
   <td colname="col2"> <p>Postal code (set by <span class="codeph"> s.zip </span>). </p> </td> 
  </tr> 
 </tbody> 
</table>
