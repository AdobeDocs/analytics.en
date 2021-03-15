---
description: Field descriptions for the General settings in dynamic tag manager, for deploying Adobe Analytics.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: General
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
---

# General

Field descriptions for the General settings in DTM, for deploying Adobe Analytics.

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL General]** 

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enable EU compliance for <span class="keyword"> Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Enables or disables tracking based on the EU privacy cookie. </p> <p>When a page is loaded, the system checks to see if a cookie called <span class="filepath"> sat_track </span> is set (or the custom cookie name specified on the <span class="wintitle"> Edit Property </span> page). Consider the following information: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> If the cookie does not exist or if the cookie exists and is set to anything but <span class="term"> true </span>, the loading of the tool is skipped when this setting is enabled. Meaning, any portion of a rule that uses the tool will not apply. </p> <p>If a rule has analytics with EU compliance on and third-party code, and the cookie is set to <span class="term"> false </span>, the third-party code still runs. However, the analytics variables will not be set. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> If the cookie exists but it is set to <span class="term"> true </span>, the tool loads normally. </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. You can accomplish this using custom code: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Character Set </p> </td> 
   <td colname="col2"> <p>Displays the available character encoding sets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Currency Code </p> </td> 
   <td colname="col2"> <p>Displays the supported currency codes for selection. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tracking Server </p> </td> 
   <td colname="col2"> <p>The domain at which the image request and cookie is written. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Tracking Server </p> </td> 
   <td colname="col2"> <p>The domain at which the image request and cookie is written. Used for secure pages. If not defined, SSL data goes to <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Center </p> </td> 
   <td colname="col2"> <p>The Adobe data center used for data collection. </p> </td> 
  </tr> 
 </tbody> 
</table>

