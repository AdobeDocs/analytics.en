---
description: The following variables and functions let you store measurement calls when the application is offline.
keywords: Analytics Implementation
seo-description: The following variables and functions let you store measurement calls when the application is offline.
seo-title: Offline tracking
solution: Analytics
title: Offline tracking
topic: Developer and implementation
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
---

# Offline tracking

The following variables and functions let you store measurement calls when the application is offline.

>[!NOTE]
>
>To enable offline tracking, your report suite must be timestamp-enabled. If timestamps are enabled on your report suite, your `trackOffline` configuration property *must* be true. if your report suite is not timestamp enabled, your `trackOffline` configuration property *must* be false. If this is not configured correctly, data will be lost. If you are not sure if a report suite is timestamp enabled, [contact Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

When enabled, Offline AppMeasurement behaves in the following way:

* The application sends a server call, but the data transmission fails. 
* AppMeasurement generates a timestamp for the current hit. 
* AppMeasurement buffers the hit data, and backs up buffered hit data to persistent storage to prevent data loss.

At each subsequent hit, or at the interval defined by `offlineThrottleDelay`, AppMeasurement attempts to send the buffered hit data, maintaining the original hit order. If the data transmission fails, it continues to buffer the hit data (This continues while the device is offline). 

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property or Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>Default: false </p> <p>Enables or disables offline tracking for the measurement library. </p> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax c">
      s.trackOffline=true; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>Default: no limit </p> <p>Maximum number of offline hits stored in the queue. </p> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax c">
      s.offlineHitLimit=100; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>Default: 0 </p> <p>Specifies a cadence (or delay), in milliseconds, for sending buffered hit data when AppMeasurement detects an active network connection. Doing so mitigates the performance impact of sending multiple hits on the application. </p> <p>For example, if offlineThrottleDelay=1000, and it takes 300ms to send the hit data, AppMeasurement waits 700ms before sending the next buffered hit. </p> 
    <codeblock class="syntax c">
      s.offlineThrottleDelay=1000; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> Manually set the online or offline state of the measurement object. The library automatically detects when the device is offline or online, so these methods are needed only if you want to force measurement offline. <span class="codeph"> forceOnline </span> is used only to return to the online state after manually going offline. </p> <p>When measurement is offline: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> If <span class="codeph"> trackOffline </span> is true: hits are stored until measurement is online. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> If <span class="codeph"> trackOffline </span> is false: hits are discarded. </li> 
    </ul> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax c">
      s.forceOffline(); 
     
s.forceOnline(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

