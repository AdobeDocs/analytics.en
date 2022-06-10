---
description: A comprehensive list and descriptions of the configuration variables, HTTP headers, and data signals in server-side forwarding calls.
title: Server-side forwarding data and code reference
feature: Server-Side Forwarding
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
---
# Server-side forwarding data and code reference

A comprehensive list and descriptions of the configuration variables, HTTP headers, and data signals in server-side forwarding calls.

## Configuration Variables {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html) (DCS). See also [Supported Attributes for DCS API calls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

|Parameter|Description|
|--- |--- |
| `d_rs` | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| `d_dst_filter` | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
| `d_dst` | Set `d_dst=1`  <br>if the request to Analytics is expecting content about the destination to be sent back to the client. |
| `d_mid` | The Experience Cloud ID passed in to Analytics. |

## HTTP Headers {#section_0549705E76004F9585224AEF872066C0}

These headers are fields contain information like requests for data and responses in an HTTP call.

| HTTP Header | Description | h_ key accepted by Audience Manager |
| --- | --- | --- |
| Host | This is set to the client's specific data collection host name specified in the Analytics host config file. It appears as `host name .demdex.net`. See [Understanding Calls to the Demdex Domain](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en). | `h_host` |
| User-Agent | Set to the User-Agent header passed in to Analytics. | `h_user-agent` |
| Accept-Language | Set to the  `Accept-Language`  header passed in to Analytics. | `h_accept-language` |
| Referer | Set to the page URL passed in to Analytics or gathered from the `Referer` header passed in to Analytics. | `h_referer` |
| Referrer | Set to the page URL passed in to Analytics or gathered from the `Referrer` header passed in to Analytics. | `h_referrer` |
| Date | Set to the `Date` header passed in to Analytics. | `h_date` |

In addition, a `h_ip` signal is generated from the IP of the host sending the request to DCS.

## Customer-Defined Signals {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_` identify customer-defined variables. See also [Supported Attributes for DCS API Calls](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Signal | Description |
| --- |--- |
| `c_browserWidth`  and `c_browserHeight` | Browser window width and height. |
| `c_campaign` | Set by `s.campaign`.|
| `c_channel` | Set by `s.channel`.|
| `c_clientDateTime` | Timestamp formatted as `dd/mm/yyy hh:mm:ss  W TZ` . `TZ` is in minutes and matches the return of the `Date.getTimezoneOffset` method.|
| `c_colorDepth` | Specified as 16- or 32-bit color.|
| `c_connectionType` | Specifies connection type. Options include:<ul><li>modem</li><li>lan</li></ul>|
| `c_contextData.*` | Examples:<ul><li>AppMeasurement: `s.contextData`</li><li>["category"] = "news";</li><li>Signal: `c_contextData.category=news`</li></ul>|
| `c_cookiesEnabled` | Specifies if cookies can be enabled. Options include: yes, no, unknown|
| `c_currencyCode` | Type of currency used for the transaction.|
| `c_evar#` | Custom evars|
| `c_events` | Set by `s.events`.|
| `c_hier#` | Custom hierarchy variables.|
| `c_javaEnabled` | Specifies if Java can be enabled. Options include: yes, no, unknown|
| `c_javaScriptVersion` | Version of JavaScript supported by a browser.|
| `c_latitude` | Numeric latitude|
| `c_linkClick` | Options include: custom, download exit|
| `c_linkCustomName` | The custom name (if any) provided for the link.|
| `c_linkDownloadURL` | The URL of download links.|
| `c_linkExitURL` | The exit link URL.|
| `c_list#` | Custom list variables.|
| `c_longitude` | Numeric longitude.|
| `c_mediaPlayerType` | For media stream tracking requests. Options include:  other, primetime|
| `c_pageName` | The page name (if set).|
| `c_pageURL` | The address of the page in the address bar of the browser.|
| `c_products` | The product string (set by `s.products`).|
| `c_prop` | Custom props.|
| `c_purchaseID` | A unique ID for the purchase.|
| `c_referrer` | The page prior to the current page.|
| `c_screenResolution` | Screen width and height (in pixels).|
| `c_server` | Web server name (set by `s.server`).|
| `c_state` | Geographic region (set by `s.state`).|
| `c_timezone` | Time offset (in hours).|
| `c_transactionID` | A unique ID for a transaction.|
| `c_zip` | Postal code (set by `s.zip`).|
