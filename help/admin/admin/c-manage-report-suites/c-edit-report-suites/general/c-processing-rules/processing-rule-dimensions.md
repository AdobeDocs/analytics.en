---
description: The dimensions that you can read and write (unless otherwise noted) using processing rules.
subtopic: Processing rules
title: Dimensions available to processing rules
feature: Processing Rules
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
---
# Dimensions available to processing rules

The dimensions that you can read and write (unless otherwise noted) using processing rules.

## Custom Values & Context Data {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Value </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Custom Value </p> </td> 
   <td colname="col2"> <p>Custom text or values typed directly in the action of a processing rule. These values are available in subsequent conditions and rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Concatenated Value </p> </td> 
   <td colname="col2"> <p>Values created by combining two values. For example, category and page name might be combined to create a subcategory. These values are available in subsequent conditions and rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modified Values </p> </td> 
   <td colname="col2"> <p>If a variable value is changed using processing rules, the changed value is used in subsequent conditions and rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Context Data Variables </p> </td> 
   <td colname="col2"> <p>Named variables that are sent with a hit. </p> <p>Note:  Any data contained in a Context Data Variable must be copied to a reporting variable to appear in a report. Context Data Variables are not viewable in any reporting interface, including ClickStream Data Feeds. </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copy a Context Data Variable to an eVar </a> </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Set an Event Using a Context Data Variable </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> Context Data Variables</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Traffic Variables {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hierarchy 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site Section </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hit Attributes {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suite ID (read-only) </p> </td> 
   <td colname="col2"> <p>The report suite the processing rule is executed on, which may not be the original report suite specified in AppMeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Name </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Note:  Link tracking calls strip the <code>pageName</code> variable before they reach processing rules. If you re-insert a page name value using processing rules, the hit is considered a page view instead of a link tracking call. Adobe recommends checking to make sure that page name is already set before you modify it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page URL </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> or the current page URL if <code> s.pageURL</code> is not specified. <p>Note:  Link tracking calls strip the <code>pageURL</code> variable before they reach processing rules. If you re-insert a page URL value using processing rules, the hit is considered a page view instead of a link tracking call. Adobe recommends checking to make sure that page URL is already set before you modify it. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query String Parameter </p> </td> 
   <td colname="col2"> <p>The value of a specified query string parameter in the current URL, or null if no parameter exists. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>If you are running JavaScript AppMeasurement H.25.2 or earlier, the page URL might be truncated after 255 characters. JavaScript AppMeasurement H.25.3 (released January 2013) and later provide the full URL to processing rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Path </p> </td> 
   <td colname="col2"> <p>The path of the page URL. The path of the URL <b>https://www.example.com/news/a.html?cid=ad1</b> is <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Domain </p> </td> 
   <td colname="col2"> <p>The full hostname, specified in the URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Root Domain </p> </td> 
   <td colname="col2"> <p>The last two sections of the hostname of the page. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Query String </p> </td> 
   <td colname="col2"> <p>The full query string of the URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer* (read-only) </p> </td> 
   <td colname="col2"> <p>HTTP referrer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Query String Parameter (read-only) </p> </td> 
   <td colname="col2"> <p>The value of a specified query string parameter in the referring URL, or null if no parameter exists. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>If you are running JavaScript AppMeasurement H.25.2 or earlier, the page URL might be truncated after 255 characters. JavaScript AppMeasurement H.25.3 (released January 2013) and later provide the full URL to processing rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Domain (read-only) </p> </td> 
   <td colname="col2"> <p>The full hostname of the referrer. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Root Domain (read-only) </p> </td> 
   <td colname="col2"> <p>The last two sections of the hostname of the referrer. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referring Query String (read-only) </p> </td> 
   <td colname="col2"> <p>Query string parameters contained in the referring URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP Address (read-only) </p> </td> 
   <td colname="col2"> <p>IP address as reported by the browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User Agent (read-only) </p> </td> 
   <td colname="col2"> <p>User agent as reported by the browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurement Code Version (read-only) </p> </td> 
   <td colname="col2"> <p>The version of the appMeasurement library used to make the request. When using image beacons, you can populate this with a custom value that is read using processing rules. This value appears at the following location in the URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conversion Variables {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign Tracking Code </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Currency Code </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>List Variables1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Purchase ID </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Transaction ID </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor State </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visitor Zip/Postal Code </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Success Events {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Processing rules can set events but cannot read them as conditions.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event 1-1000 </p> <p>(For SiteCatalyst 15 customers, Event 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase, scView, scAdd, and other cart events </p> </td> 
   <td colname="col2"> <p>Predefined events. </p> </td> 
  </tr> 
 </tbody> 
</table>
