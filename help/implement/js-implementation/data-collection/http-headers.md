---
description: HTTP request and response headers are used to collect additional data beyond what is collected by AppMeasurement. This section describes the headers used during data collection.
keywords: Analytics Implementation
seo-description: HTTP request and response headers are used to collect additional data beyond what is collected by AppMeasurement. This section describes the headers used during data collection.
seo-title: Data collection HTTP headers
solution: Analytics
title: Data collection HTTP headers
topic: Developer and implementation
uuid: 3325e13c-b300-46e4-a592-3a83ed59718b
---

# Data collection HTTP headers

HTTP request and response headers are used to collect additional data beyond what is collected by AppMeasurement. This section describes the headers used during data collection.

## HTTP Request Headers {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>Header</b> </td> 
   <td> <b>Usage</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>Reading cookies previously created by our data collection servers. </p> <p> As of 2014, Adobe servers will discard all cookies that accompany a server call except those set by Adobe. See <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external"> Cookies Used in the Experience Cloud</a> for the full list of Adobe's cookies. </p> </td> 
  </tr> 
  <tr> 
   <td> User-Agent </td> 
   <td> Used for browser, operating system, and mobile device detection. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Used as an alternative to User-Agent for correct browser, operating system, and mobile device detection for some browsers like OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Used as an alternative to User-Agent for correct browser, operating system, and mobile device detection for some browsers like OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> Used as an alternative to User-Agent for correct browser, operating system, and mobile device detection for some browsers like OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Used as an alternative to User-Agent for correct browser, operating system, and mobile device detection for some browsers like OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Used as an alternative to User-Agent for correct browser, operating system, and mobile device detection for some browsers like OperaMini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> Used as an alternative was to identify the operating system. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixels </td> 
   <td> Used as an alternate source for the screen resolution of the client screen. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Used as an alternate source for the color depth of the client screen. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Detecting that the data collection request was made as part of pre-fetching a webpage. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> Detecting that the data collection request was made as the browser was showing a preview of a webpage. </td> 
  </tr> 
  <tr> 
   <td> Accept </td> 
   <td> Used to identify the image formats supported by the browser so we know if we need to send back a GIF or WBMP image. </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> Used as a fallback for getting information about the page URL the data collection request was made from when it wasn't passed in on the query-string or when it's different from the value in the query-string. </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> Used to find the correct IP address for the client that made the data collection request. The IP address is used to generate geographic region, mobile carrier, and other reports. </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Implementations using dynamic variables have the option of reading in other HTTP request headers not listed above.

## HTTP Response Headers {#section_A9C7035198C84037A21A8033CC408F0E}

|  **Header** | **Usage** |
|---|---|
|  Access-Control-Allow-Origin  | Used to enable support for cross-origin resource sharing style data collection requests to our servers.  |
|  Expires  | Browser caching control.  |
|  Last-Modified  | Browser caching control.  |
|  Cache-Control  | Browser caching control.  |
|  Pragma  | Browser caching control.  |
|  ETag  | Browser caching control.  |
|  Vary  | Browser caching control.  |
|  P3P  | Provides the default or custom P3P policy for the data collection request.  |
|  Status  | Contains "SUCCESS" or "FAILURE" status for a no content request. Used only when the request specifies that no content should be returned.  |
|  Reason  | Contains the reason for the failure status of a no content request. Used only when the request specifies that no content should be returned.  |
|  Location  | Used to redirect the client making the data collection request off to a different URL. An example is our cookie handshake to detect the ability to set the visitor ID cookie.  |
|  Content-Type  | Specifies the type of content sent back to the client (GIF, text, Javascript, etc).  |
|  Content-Length  | Specifies the size of the content sent back to the client.  |

> [!NOTE] Other HTTP headers may be set in the response for internal status monitoring. Some of these headers might be returned to the browser, but it is not necessary that they receive them.
