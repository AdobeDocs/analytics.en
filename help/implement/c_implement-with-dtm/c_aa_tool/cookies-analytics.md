---
description: Field descriptions for the Cookies global settings used for deploying Dynamic Tag Management in Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
seo-description: Field descriptions for the Cookies global settings used for deploying Dynamic Tag Management in Adobe Analytics.
seo-title: Cookies
solution: Marketing Cloud,Analytics,Dynamic Tag Management
title: Cookies
uuid: 4020053e-3531-4d50-983f-97cdd6eec1fd
index: y
internal: n
snippet: y
---

# Cookies

Field descriptions for the Cookies global settings used for deploying Dynamic Tag Management in Adobe Analytics.

 **[!UICONTROL  *`Property`*]** > **[!UICONTROL   ![](assets/settings_gear.png)

Edit Tool]** > **[!UICONTROL Cookies]** 

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visitor ID </td> 
   <td colname="col2"> <p>Unique value that represents a customer in both the online and offline systems. </p> <p>See <a href="visitorID.md#concept_CD273CC915CC4ABD8F52E4209FF9557E" format="dita" scope="local"> visitorID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitor Namespace </td> 
   <td colname="col2"> <p>Variable to identify the domain with which cookies are set. </p> <p>See <a href="visitorNamespace.md#concept_8369DDB3830C4BF2905F1CFC8C8B0D92" format="dita" scope="local"> visitorNamespace</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Domain Periods </td> 
   <td colname="col2"> <p>The domain on which the Analytics cookie <span class="codeph"> s_cc</span> and <span class="codeph"> s_sq</span> are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. </p> <p>See <a href="cookiedomainperiods.md#concept_F17A59C7D8F54F5897AD40980B6725EB" format="dita" scope="local"> s.cookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP Domain Periods </td> 
   <td colname="col2"> <p>The <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<span class="codeph"> s_sq</span>, <span class="codeph"> s_cc</span>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>See <a href="fpCookieDomainPeriods.md#concept_0A25BD152B0744989E7C662A95448274" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transaction ID </td> 
   <td colname="col2"> <p>Unique value that represents an online transaction that resulted in offline activity. </p> <p>See <a href="transactionID.md#concept_FBFA55E137E644A2BD97B41E92F6AFEF" format="dita" scope="local"> transactionID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie Lifetime </td> 
   <td colname="col2"> <p>Determines the life span of a cookie. </p> <p>See <a href="cookielifetime.md#concept_8347C6648B0E4D4996E2F223C34B9A3D" format="dita" scope="local"> s.cookieLifetime</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

