---
description: You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.
seo-description: You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.
seo-title: Requirements for server-side forwarding
solution: Audience Manager
title: Requirements for server-side forwarding
uuid: f101733d-69b6-4427-94e1-ce08ad4c1faa
index: y
internal: n
snippet: y
---

# Requirements for server-side forwarding

You must meet these Experience Cloud solution, service, and code requirements to implement server-side forwarding. These requirements also include instructions on how to check for code versions and where to get the latest code libraries.

<table id="table_43315E680771401E8A585466781A454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Requirement Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Solution Requirements</b> </p> </td> 
   <td colname="col2"> <p>Server-side forwarding works with <a href="http://www.adobe.com/data-analytics-cloud/analytics.html" format="http" scope="external"> Analytics</a> and <a href="http://www.adobe.com/data-analytics-cloud/audience-manager.html" format="http" scope="external"> Audience Manager</a> and/or <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html" format="html" scope="external"> Audiences</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Service Requirements</b> </p> </td> 
   <td colname="col2"> <p>Server-side forwarding requires the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service</a>. The <span class="keyword"> Experience Cloud</span> ID service provides a universal ID that identifies site visitors across all the solutions in the <span class="keyword"> Experience Cloud</span>. You need to implement the ID service before server-side forwarding will work. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Code Versions</b> </p> </td> 
   <td colname="col2"> <p>Server-side forwarding requires version 1.5 (or newer) of the code libraries listed below. As a best practice, we recommending using the latest versions rather than these required minimums. </p> <p> 
     <ul id="ul_63489ED3D7DA47B48F55F45BF8695148"> 
      <li id="li_323164F07AFA4260AE1695A6801DF31B"><span class="codeph"> AppMeasurement.js</span> </li> 
      <li id="li_75C28BEF1D9F4D56B06848CC1D26BB84"><span class="codeph"> AppMeasurement_Module_AudienceManagement.js</span> </li> 
      <li id="li_C86A331363C1486C8EBAF73BF2E0D6C1"><span class="codeph"> VistorAPI.js</span> </li> 
     </ul> </p> <p><b>Determine Your Code Library Version</b> </p> <p>Any tool that monitors the HTTP requests made by a browser can show you the version number for your AppMeasurement and Visitor API code. The <span class="codeph"> AppMeasurement_Module_AudienceManagement.js</span> does not contain or return a version ID. The following examples show you what the version IDs for look like for <span class="codeph"> AppMeasurement.js</span> and <span class="codeph"> VisitorAPI.js</span> code. </p> <p> 
     <ul id="ul_1A994C81EEBE4D47BBDB7D7A319DAC21"> 
      <li id="li_9D339D838598424FBD732F411812CEEA"><span class="codeph"> AppMeasurement.js</span>: The <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> Adobe Debugger</a> returns the AppMeasurement version like this: <span class="codeph"> Version of Code | JS-1.5.1</span>. Other tools may use a different label, but the value always follows the pattern <span class="codeph"> JS-X.X.X</span>, where <span class="codeph"> X</span> is a version number. </li> 
      <li id="li_EB3434FD4EA84081A547F60F04F16123"><span class="codeph"> VisitorAPI.js</span>: Look for the <span class="codeph"> d_visid_ver</span> parameter. It will show you the Visitor ID service like this: <span class="codeph"> d_visid_ver: 1.5.5</span>. Visitor API code older than version 1.5.2 did not include a version number. You're probably using an older code library (and need to upgrade) if your monitoring results do not return a version number. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

