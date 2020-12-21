---
description: Field descriptions for the Cookies global settings used for deploying Dynamic Tag Management in Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics
title: Cookies
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
---

# Cookies

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

 *`Property`* > Edit Tool > Cookies 

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
   <td colname="col2"> <p>Unique value that represents a customer in both the online and offline systems. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitor Namespace </td> 
   <td colname="col2"> <p>Variable to identify the domain with which cookies are set. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Domain Periods </td> 
   <td colname="col2"> <p>The domain on which the Analytics cookie <code> s_cc</code> and <code> s_sq</code> are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FP Domain Periods </td> 
   <td colname="col2"> <p>The <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> adobedc.net</span> domain, or the legacy (but still valid) <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>See <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  > s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transaction ID </td> 
   <td colname="col2"> <p>Unique value that represents an online transaction that resulted in offline activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cookie Lifetime </td> 
   <td colname="col2"> <p>Determines the life span of a cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

