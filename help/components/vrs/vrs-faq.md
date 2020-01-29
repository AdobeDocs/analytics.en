---
description: Tips and Best Practices for new users of virtual report suites.
keywords: Virtual Report Suite
title: VRS FAQs
topic: Reports and analytics
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
---

# VRS FAQs

Tips and Best Practices for new users of virtual report suites.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Should I consolidate my implementation from multiple report suites into a single "global" report suite and then use virtual report suites to expose different segments of data to my users?</b> </td> 
   <td colname="col2"> <p>Maybe. Here are some circumstances under which you should <b>consider continuing with individual report suites</b>: </p> 
    <ul> 
     <li>If you have variables/dimensions with a large number of unique values, consolidating into a single report suite may cause you to exceed monthly unique value limits in this global suite, leading to truncation ("Low Traffic" as a line item in reports). </li> 
     <li>If you require real-time or "Current Data" reporting for individual segments (e.g. brands, business units, etc.) of your data. </li> 
     <li>If your various report suites each have unique requirements for tracking (i.e., if they use Adobe Analytics variables and events very differently), note that consolidating to a global report suite will not grant you additional variables or events for tracking. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Which settings on virtual report suites are inherited from the parent report suite? </b> </td> 
   <td colname="col2"> <p>A virtual report suite (VRS) inherits most of the service levels of the parent report suite, such as eVar settings, Processing Rules, Classifications, etc. </p> <p>The following settings are <b>NOT</b> inherited: </p> 
    <ul> 
     <li>Report suite ID </li> 
     <li>Report suite name </li> 
     <li>Permission groups (virtual report suites can be assigned to their own permission groups) </li> 
    </ul> <p>Note:  This does not include most user-created entities like Bookmarks, Dashboards, Scheduled Reports, etc.; these items are not inherited from the parent and can be created and used against the VRS specifically (more detail in the next question). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>How does working with a virtual report suite differ from working with a base report suite in the Analytics UI?</b> </td> 
   <td colname="col2"> <p>Once created, a virtual report suite is treated just like a base report suite throughout the UI and is generally supported for most extended features. For example: </p> 
    <ul> 
     <li>Virtual report suites show up in the Report Suite selector and can be selected individually just like any other base report suite. </li> 
     <li>DL Reports, Bookmarks, Dashboards, Targets, Alerts, Segments, Calculated Metrics, etc. can all be created against a virtual report suite and behave independently of the parent. </li> 
     <li>Virtual report suites can be individually added to Permissions Groups just like any other report suite. </li> 
     <li>Segments can still be applied when running reports in the context of a VRS; they will automatically be stacked with the virtual report suite's segment(s) when the report data is being retrieved. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>How are virtual report suites treated in the Admin Console and Admin API? Can I save features against them like base report suites? </b> </td> 
   <td colname="col2"> <p>No, virtual report suites are <b>not supported for most Admin features</b>. As mentioned above, a VRS inherits most service levels and features from the parent (for example, eVar settings, Processing Rules, Classifications, etc.), so to make a changes to these inherited settings on a VRS, you must alter the parent report suite. </p> <p>As a result, virtual report suites are shown in the UI <b>only here</b>: </p> 
    <ul> 
     <li>The Virtual Report Suite Manager, where you create and edit VRSs. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics </span>  &gt; <span class="uicontrol"> Components </span>  &gt; <span class="uicontrol"> Virtual Report Suites </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> The User Management interface, where you edit custom permissions groups. This allows VRS accounts to be added to a permissions group and could be used to create a group that only has access to virtual report suites (if the Admin wanted to deny access to the parent and only allow users access to specific segments). <p>( <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> User Management </span> </span>) </p> </li> 
    </ul> <p>Note:  When you use the Web Services API and attempt to save Feature settings against a VRS, an exception will be thrown. Features can only be set against a base report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I checked "start new visit on launch." Why do I see visits still much higher than launches?</b> </td> 
   <td colname="col2"> <p> When "start new visit on launch" is checked, the timeout still applies. So, if a user is using the app for ten minutes with a one minute break in between each action, a new visit starts on launch, then nine additional visits are created when the visit times out. To keep launches and visits as close as possible when using the "start new visit on launch" option, you should use a timeout that is longer than the session timeout set in the SDK . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I set "start new visit on launch" and set a longer timeout than my SDK. Why are my launches still much lower than visits?</b> </td> 
   <td colname="col2"> <p> If the timeout is higher than the value set in the SDK, it is very likely that your app is sending in hits while in the background and these hits are registering as new visits. Check for this by using the hit type dimension on the parent report suite to see if there are any background hits. </p> <p> <p>Note: Background and foreground hits are only differentiated in version 4.13.6 and higher of the SDK. If you are on a lower version, all hits show as foreground. If you are on the correct version of the SDK, you should enable the "Prevent background hits from starting a new visit" setting. </p> </p> <p> <p>Note: If you have disabled legacy processing for background hits in the admin console, they will not show up in the parent report suite but will appear in the virtual report suite. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> What version of the SDK do I need to have to track background hits?</b> </td> 
   <td colname="col2"> <p> You must be on version 4.13.6 or higher of the SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>

