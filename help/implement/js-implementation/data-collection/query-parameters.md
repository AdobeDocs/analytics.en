---
description: The following tables lists the query parameter that contains the value for each analytics variable that is sent to data collection.
keywords: Analytics Implementation
seo-description: The following tables lists the query parameter that contains the value for each analytics variable that is sent to data collection.
seo-title: Data collection query parameters
solution: Analytics
title: Data collection query parameters
topic: Developer and implementation
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
index: y
internal: n
snippet: y
---

# Data collection query parameters

The following tables lists the query parameter that contains the value for each analytics variable that is sent to data collection.

This information can be used when debugging using [Packet Analyzers](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258), when manually constructing image requests, or when using [Dynamic Variables](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262). 

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parameter </th> 
   <th class="entry"> Analytics Variable </th> 
   <th class="entry"> Report Populated </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> None </td> 
   <td colname="col3"> None </td> 
   <td colname="col4"> Audience Manager Location Hint (used in Experience Cloud Shared Profile integration) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> None </td> 
   <td colname="col3"> None </td> 
   <td colname="col4"> Audience Manager Blob (used in Experience Cloud Shared Profile integration) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> None </td> 
   <td colname="col3"> None </td> 
   <td colname="col4"> Analytics visitor ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> None </td> 
   <td> None </td> 
   <td> Indicates the beginning of an image request. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> None </td> 
   <td> None </td> 
   <td> Indicates the end of an image request, meaning the request was not truncated. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Browser Height </td> 
   <td> Browser window height (in pixels) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Browser Width </td> 
   <td> Browser window width (in pixels) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Monitor Color Depths </td> 
   <td> Color quality (in bits) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> c. <span class="varname"> [key] </span> </span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>None </p> </td> 
   <td> <p>Key-values pairs are specified in one of the following formats: </p> <p> <span class="codeph"> &lt;my.a&gt;red&lt;/my.a&gt; </span> </p> <p>or: </p> <p> <span class="codeph"> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </span> </p> <p>Each of these examples result in a context data value of <span class="codeph"> my.a = red </span>. Multiple key-value pairs can be specified. </p> <p>In the query string, this context data variable would appear as <span class="codeph"> c.my.a=red </span> </p> </td> 
  </tr> 
  <tr> 
   <td> c1-c75 </td> 
   <td> s.prop1-s.prop75 </td> 
   <td> All Custom Traffic reports </td> 
   <td> Traffic variables used in custom traffic reporting </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> None </td> 
   <td> The type of currency used on the site </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> None </td> 
   <td> Indicates the number of periods in a domain for cookie tracking; manually set. </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> None </td> 
   <td> The character encoding of the image request </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime (s_vi cookie lifetime in seconds) </td> 
   <td> None </td> 
   <td> The lifetime of the visitor cookie. </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> Site Content | Site Sections </td> 
   <td> The Site Sections variable used in traffic reporting </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> Hit Type </td> 
   <td> Hit Type </td> 
   <td> Indicates whether the behavior is a result of direct interaction foreground or information the device is sending without direct interaction background. </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Connection Types </td> 
   <td> Connection Type (Modem, LAN, etc; can only populate in IE browsers) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> D </span> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> None </td> 
   <td> <p>See <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> Dynamic Variables </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events or ev </td> 
   <td> s.events </td> 
   <td> Site Traffic | Purchases, Shopping Cart, Custom Events </td> 
   <td> The commerce and custom events that occurred on the page; used in conversion reports </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> None </td> 
   <td> None </td> 
   <td> The current URL of the page, up to 255 bytes. </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> None </td> 
   <td> None </td> 
   <td> URLs longer than 255 bytes are split, with the first 255 bytes appearing in the g parameter, with the remaining bytes appearing later in the query string in the -g= query parameter. </td> 
  </tr> 
  <tr> 
   <td> h1-h5 </td> 
   <td> s.hier1-s.hier5 </td> 
   <td> Site Content | Hierarchy reports </td> 
   <td> Hierarchy variables; used in traffic reporting </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> None </td> 
   <td> Visitor Profile | Visitor Home Page </td> 
   <td> Indicates if current page is browser's home page (Y or N; can only populate in IE browsers) </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Javascript Version </td> 
   <td> Shows the current Javascript version installed (generally 1.x) </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Cookies </td> 
   <td> Are cookies supported in the browser (Y, N or U) </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1-s.list3 </td> 
   <td> Custom Conversion </td> 
   <td> A delimited list of values that are passed into a variable, then reported as individual line items for reporting. </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> None </td> 
   <td> None </td> 
   <td> Experience Cloud Visitor ID </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> None </td> 
   <td> None </td> 
   <td> Indicates whether the image request originated from JS file (1 or 0) </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> None </td> 
   <td> Specifies what domain the cookies are set on </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> Site Content | Links | ClickMap </td> 
   <td> Object identifier for last page; used in ClickMap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> None </td> 
   <td> Site Content | Links | ClickMap </td> 
   <td> Object tag name for last page; used in ClickMap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Netscape Plug-Ins </td> 
   <td> Semicolon delimited browser plug-in names </td> 
  </tr> 
  <tr> 
   <td> pageName (or gn) </td> 
   <td> s.pageName </td> 
   <td> Site Content | Pages </td> 
   <td> The page's designated name in reporting </td> 
  </tr> 
  <tr> 
   <td> pageType (or gt) </td> 
   <td> s.pageType </td> 
   <td> Site Content | Pages Not Foun </td> 
   <td> Indicates whether it is a 404 page or not (Either 'error' or blank) </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> None </td> 
   <td> None </td> 
   <td> Only occurs for new visitors; prevents infinite redirects (Always true) </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> Site Content | Links | Exit Links, File Downloads, Custom Links </td> 
   <td> Determines the type of custom link hit fired </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> None </td> 
   <td> Site Content | Links | Exit Links, File Downloads, Custom Links </td> 
   <td> URL the custom link hit occurred on </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> None </td> 
   <td> Site Content | Links | Exit Links, File Downloads, Custom Links </td> 
   <td> Custom link friendly name </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> None </td> 
   <td> All video reports </td> 
   <td> Used to track milestones in legacy video reporting; deprecated with v15 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> None </td> 
   <td> None </td> 
   <td> For Adobe use only. Do not alter. </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> None </td> 
   <td> Site Content | Links | ClickMap </td> 
   <td> Page identifier for last page; used in ClickMap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> None </td> 
   <td> Site Content | Links | ClickMap </td> 
   <td> Page identifier type for last page; used in ClickMap </td> 
  </tr> 
  <tr> 
   <td> products (or pl) </td> 
   <td> s.products </td> 
   <td> Products | Products </td> 
   <td> Products variable used in conversion reporting </td> 
  </tr> 
  <tr> 
   <td> purchaseID (or pi) </td> 
   <td> s.purchaseID </td> 
   <td> None </td> 
   <td> Used to deduplicate purchases, preventing revenue inflation </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> All traffic sources reports </td> 
   <td> Referring URL </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Monitor Resolutions </td> 
   <td> Screen resolution (width x height) </td> 
  </tr> 
  <tr> 
   <td> server (or sv) </td> 
   <td> s.server </td> 
   <td> Site Content | Servers </td> 
   <td> The page's server; used in traffic reporting </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> Visitor Profile | Visitor State </td> 
   <td> Specifies the state as defined by the variable. </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (automatic, sent with every hit that does not have a custom timestamp) </td> 
   <td> None </td> 
   <td> <p>The <span class="codeph"> t </span> parameter is in the following format: </p> 
    <codeblock>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </codeblock> <p>Where D is a number in the range <span class="codeph"> 0-6 </span> specifying the day of the week, and <span class="codeph"> OFFSET </span> represents: </p> 
    <codeblock>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </codeblock> <p> For example: </p> 
    <codeblock>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ts </span> </td> 
   <td> <p>timestamp </p> </td> 
   <td> None </td> 
   <td> <p>The custom timestamp calculated and sent in with the hit. Typically used for offline tracking. </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> None </td> 
   <td> Visitor Profile | Technology | Java </td> 
   <td> Java enabled (Y or N) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> Campaigns | Tracking Codes </td> 
   <td> The campaign variable used in conversion reporting </td> 
  </tr> 
  <tr> 
   <td> v1-v75 </td> 
   <td> s.eVar1-s.eVar75 </td> 
   <td> All Custom Conversion reports </td> 
   <td> Conversion variables used in custom conversion reporting </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> None </td> 
   <td> The visitor's unique ID as set in the <a href="visitorID.md#concept_CD273CC915CC4ABD8F52E4209FF9557E" format="dita" scope="local"> visitorID </a> variable. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> None </td> 
   <td> Visitor migration key; used to migrate from third-party to first-party cookies. Deprecated. </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> None </td> 
   <td> Used in Genesis integrations </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> None </td> 
   <td> The transaction ID used to link online data to offline data </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> Visitor Profile | Visitor ZIP/Postal Code </td> 
   <td> Determines the zip code as defined by the variable </td> 
  </tr> 
  <tr> 
   <td> /5/ (for mobile protocol) or /1/ (for non-mobile protocol) in the image request URL. </td> 
   <td> None </td> 
   <td> None </td> 
   <td> <p> Controls the order in which cookies and other methods are used to identify visitors. </p> </td> 
  </tr> 
 </tbody> 
</table>

