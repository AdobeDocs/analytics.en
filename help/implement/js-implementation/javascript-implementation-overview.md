---
description: To begin using Analytics, data must be sent to a report suite to display in reporting.
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Experience Cloud id service;visitorapi.js;caching;appmeasurement compression
seo-description: To begin using Analytics, data must be sent to a report suite to display in reporting.
seo-title: JavaScript implementation overview
solution: Analytics
title: JavaScript implementation overview
topic: Developer and implementation
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
index: y
internal: n
snippet: y
---

# JavaScript implementation overview

To begin using Analytics, data must be sent to a report suite to display in reporting.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). However, in some cases, you might want to implement Analytics using the older JavaScript method.

>[!NOTE]
>
>This section describes the legacy method of implementing Analytics. All Analytics customers have access to [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) which is the standard method to deploy Experience Cloud tags.

## Implementation Steps {#section_73961BAD5BB4430A95E073DE5C026277}

To successfully implement a page with code to collect data, you must have access to your hosting servers to upload new content to your website. It is also useful to have an existing site to implement code.

The following steps walk you through a basic Analytics implementation. 

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> Step </th> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> Download AppMeasurement for JavaScript and the Visitor ID service. </td> 
   <td colname="col2"> <p>The download is available in <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external"> Code Manager </a>. </p> <p>This download zip contains several files. <span class="codeph"> AppMeasurement.js </span> and <span class="codeph"> VisitorAPI.js </span> are the relevant files when implementing Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> Set up the Experience Cloud ID service. </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Experience Cloud ID Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>In <span class="codeph"> VisitorAPI.js </span>, add the following visitor ID initialization code at the beginning of the file: </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure /* == DO NOT ALTER ANYTHING BELOW THIS LINE ==
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <span class="codeph"> "INSERT-MCORG-ID-HERE" </span> - (Required) This Adobe Experience Cloud Organization ID is sent to your administrator when your company is provisioned for the Adobe Experience Cloud. </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <span class="codeph"> "INSERT-TRACKING-SERVER-HERE" </span> - (Required) Your Analytics tracking server. </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <span class="codeph"> "INSERT-SECURE-TRACKING-SERVER-HERE" </span> - (Required if ssl is enabled) Your Analytics secure tracking server. </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> Update <span class="codeph"> AppMeasurement.js </span>. </td> 
   <td colname="col2"> <p>Copy the <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local"> Example AppMeasurement.js Code </a> and paste it at the beginning of your <span class="codeph"> AppMeasurement.js </span> file. At a minimum, update the following variables: </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <span class="codeph"> s.account="INSERT-RSID-HERE" </span> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <span class="codeph"> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </span> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <span class="codeph"> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </span> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <span class="codeph"> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </span> </li> 
    </ul> <p> See <a href="https://marketing.adobe.com/resources/help/kb/en_US/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. If they are not set correctly, data will not be collected by your implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> Host <span class="codeph"> AppMeasurement.js </span> and <span class="codeph"> VisitorAPI.js </span>. </td> 
   <td colname="col2"> <p>These core JavaScript files must be hosted on a web server that is accessible to all pages on your site. You need the path to these files in the next step. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> Reference <span class="codeph"> AppMeasurement.js </span> and <span class="codeph"> VisitorAPI.js </span> on all site pages. </td> 
   <td colname="col2"> <p> Include the Visitor ID Service by adding the following line of code in the <span class="codeph"> &lt;head&gt; </span> or &lt;body&gt; tag on each page. <span class="codeph"> VisitorAPI.js </span> must be included before <span class="codeph"> AppMeasurement.js </span>: </p> 
    <code class="syntax html">
      &lt;script&nbsp;language="JavaScript"&nbsp;type="text/javascript"&nbsp; src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"&gt;&lt;/script&gt; 
    </code> <p> Include AppMeasurement for JavaScript by adding the following line of code in the <span class="codeph"> &lt;head&gt; </span> or <span class="codeph"> &lt;body&gt; </span> tag on each page: </p> 
    <code class="syntax html">
      &lt;script&nbsp;language="JavaScript"&nbsp;type="text/javascript"&nbsp; src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"&gt;&lt;/script&gt; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> Update and deploy page code. </td> 
   <td colname="col2"> <p>Copy the <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local"> Example Page Code </a> and paste it just after the opening <span class="codeph"> &lt;body&gt; </span> tag on each page you want to track. At a minimum, update the following variables: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <span class="codeph"> var s=s_gi("INSERT-RSID-HERE") </span> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <span class="codeph"> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> Use the DigitalPulse Debugger to verify that data is being sent. </td> 
   <td colname="col2"> <p>Install the <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local"> Adobe Debugger </a> bookmarklet. After it is installed, load a page where you have deployed page code and then open the debugger. The debugger displays details about the collection data that was sent. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caching {#section_4E2D1D962DF046418134C43CFC49AD4A}

The JavaScript file is cached in the visitor's browser after it is initially loaded, and is typically downloaded no more than once per session. The file is not downloaded on each page, even though it is used by every page on the site. On most websites, users average more than a few page views per session, so transferring JavaScript that is used multiple times into this file can result in less overall downloaded data.

## JavaScript for AppMeasurement Compression {#section_C10BBC84C81C414088F97363D29E021B}

If you are concerned about page weight (size) of H Code (AppMeasurement for JavaScript 1.0 is pre-compressed), Adobe recommends that you consider compressing the file using GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression to compress and decompress the core [!DNL s_code.js] JavaScript file.

The following links help explain how you can use GZIP functionality on your site to handle compression of the [!DNL s_code.js] JavaScript code:

[Apache Module mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Enabling gzip compression with Tomcat and Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/) 
