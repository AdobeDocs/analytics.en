---
description: Data Sources supports the following variables when processing data as a standard server call (Generic > Full Processing).
title: Full processing
topic-fix: Developer and implementation
exl-id: 9eb8c754-f4de-4483-934e-3f79134516ca
---
# Full processing

>[!IMPORTANT]
>
>Adobe recommends customers use the [Bulk Data Insertion API (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) instead of full processing data sources. Adobe plans to deprecate full processing data sources on July 31, 2021. [Learn more](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md)

Data Sources supports the following variables when processing data as a standard server call (Generic > Full Processing).

Full Processing data sources data is processed as if it were received by Adobe servers at the time specified (each hit contains a timestamp).

* [Visitor Profile](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8) 
* [Column Reference](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## Visitor Profile {#section_6065627D0C144506965F562C80AE67F8}

Full processing data sources data is processed using separate visitor profiles, so even if the visitor ID in uploaded data matches data collected using JavaScript or other AppMeasurement library, the visitor profiles are not connected from an eVar allocation perspective.

For example, a user with a visitor ID of `"user@example.com"` visits your site from a marketing campaign named "Spring Sale", which is stored in the campaign variable. If you later upload a transaction using the same visitor ID, the "Spring Sale" campaign does not receive credit for any revenue or success events uploaded using full processing data sources.

## Column Reference {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript Variable </th> 
   <th colname="col2" class="entry"> Full Processing Column Variable </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>Conversion campaign tracking code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>channel </p> </td> 
   <td colname="col2"> <p>channel </p> </td> 
   <td colname="col3"> <p>Channel string (for example, Sports Section). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>Note:  This variable is also supported by Standard data sources as <code> currency code </code>. </p> </td> 
   <td colname="col3"> <p>Revenue currency code (for example, USD). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>date </p> </td> 
   <td colname="col3"> <p>Use the ISO 8601 date format of <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (for example, <code> 2013-09-01T12:00:00-07:00 </code>), or Unix Time Format (the number of seconds elapsed since January 1, 1970). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>, i.e. &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>Conversion eVar name. You can have up to 75 eVars ( <span class="varname"> eVar1 </span> - <span class="varname"> eVar75 </span>). </p> <p>You can specify the eVar name (eVar12) or a friendly name (Ad Campaign 3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>Events string, formatted using the same syntax as the <a href="https://experienceleague.adobe.com/docs/ analytics/implementation/vars/page-vars/events/event-serialization.html"  > s.events </a> variable. </p> <p>For example: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>, i.e. &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>Hierarchy name. You can have up to 5 hierarchies ( <span class="varname"> hier1 </span> - <span class="varname"> hier5 </span>). </p> <p>You can specify the default hierarchy name ( <span class="varname"> hier2 </span>) or a friendly name ( <span class="term"> Yankees </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>Name of link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>Type of link. Supported values include: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: Download link </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: Exit link </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: Custom link. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>HREF of link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>Page Name </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>Page Type ("Error Page"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>Page URL (for example, <code>https://www.example.com/index.html)</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>Product list (for example, <code> "Sports;Ball;1;5.95"</code>). Can hold a maximum value of 4096 bytes per row.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>, i.e. &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>Property# string (for example, <span class="term"> Sports Section </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>Purchase ID number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>Report suite ID(s) to which to attribute the hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>Server string. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>Conversion state string. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>Conversion zip code. </p> </td> 
  </tr> 
 </tbody> 
</table>

The following table contains traffic variables that are populated automatically when using the JavaScript libraries. These properties do not have associated variables but can be imported using data sources.

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Full Processing Column Variable </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>Browser height in pixels (for example, 768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>Browser width in pixels (for example 1024). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>The supported cahracter set for your Web site. For example, UTF-8, ISO-8859-1, and so forth. </p> <p>See the <a href="https://experienceleague.adobe.com/docs/ analytics/implementation/vars/config-vars/configuration-variables.html#concept_E65B9A8F75C3482C87D0D455805F89BD"  > Multi-Byte Character Sets </a> (Internationalization) whitepaper for a complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>Object identifier for visitor click map (oid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>Object identifier type for visitor click map (oidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>Page identifier for visitor click map (pid) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>Page identifier type for visitor click map (pidt) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>Source index for visitor click map (oi) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>Object tag name for visitor click map (ot) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>Monitor color depth in bits (for example, 24). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>Visitor's connection type ( <span class="term"> lan </span> or <span class="term"> modem </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>Y or N for if the visitor supports first party session cookies. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>The default currency code used on your Web site. </p> <p>For example, USD=U.S. dollars, EUR = Euros, JPY = Japanese Yen, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y or N -- is the current page the visitor's homepage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>Y or N -- does the visitor have Java enabled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>JavaScript version (for example, 1.3). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>Semicolon separated list of browser plug-in names. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>Property values for your properties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>URL for page referrer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>Monitor resolution (for example, 1024x768). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>Marketing reports XML request version number (for example, 1.0). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>Visitor's time zone offset from GMT in hours (for example, -8). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>Visitor ID number. </p> </td> 
  </tr> 
 </tbody> 
</table>
