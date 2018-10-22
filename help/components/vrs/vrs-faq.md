---
description: Tips and Best Practices for new users of virtual report suites.
keywords: Virtual Report Suite
seo-description: Tips and Best Practices for new users of virtual report suites.
seo-title: VRS FAQs
solution: Analytics
title: VRS FAQs
topic: Reports and analytics
uuid: f249db78-8b1f-4fbc-8298-a8ce122be3b9
index: y
internal: n
snippet: y
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
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">If you have variables/dimensions with a large number of unique values, consolidating into a single report suite may cause you to exceed monthly unique value limits in this global suite, leading to truncation ("Low Traffic" as a line item in reports). </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">If you require real-time or "Current Data" reporting for individual segments (e.g. brands, business units, etc.) of your data. </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">If your various report suites each have unique requirements for tracking (i.e., if they use Adobe Analytics variables and events very differently), note that consolidating to a global report suite will not grant you additional variables or events for tracking. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Which settings on virtual report suites are inherited from the parent report suite? </b> </td> 
   <td colname="col2"> <p>A virtual report suite (VRS) inherits most of the service levels of the parent report suite, such as eVar settings, Processing Rules, Classifications, etc. </p> <p>The following settings are <b>NOT</b> inherited: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">Report suite ID </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">Report suite name </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">Permission groups (virtual report suites can be assigned to their own permission groups) </li> 
    </ul> <p>Note:  This does not include most user-created entities like Bookmarks, Dashboards, Scheduled Reports, etc.; these items are not inherited from the parent and can be created and used against the VRS specifically (more detail in the next question). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>How does working with a virtual report suite differ from working with a base report suite in the Analytics UI?</b> </td> 
   <td colname="col2"> <p>Once created, a virtual report suite is treated just like a base report suite throughout the UI and is generally supported for most extended features. For example: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">Virtual report suites show up in the Report Suite selector and can be selected individually just like any other base report suite. </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">DL Reports, Bookmarks, Dashboards, Targets, Alerts, Segments, Calculated Metrics, etc. can all be created against a virtual report suite and behave independently of the parent. </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">Virtual report suites can be individually added to Permissions Groups just like any other report suite. </li> 
     <li id="li_764475FD352C434D92E876E30699F280">Segments can still be applied when running reports in the context of a VRS; they will automatically be stacked with the virtual report suite's segment(s) when the report data is being retrieved. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>How are virtual report suites treated in the Admin Console and Admin API? Can I save features against them like base report suites? </b> </td> 
   <td colname="col2"> <p>No, virtual report suites are <b>not supported for most Admin features</b>. As mentioned above, a VRS inherits most service levels and features from the parent (for example, eVar settings, Processing Rules, Classifications, etc.), so to make a changes to these inherited settings on a VRS, you must alter the parent report suite. </p> <p>As a result, virtual report suites are shown in the UI <b>only here</b>: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">The Virtual Report Suite Manager, where you create and edit VRSs. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics </span>  &gt; <span class="uicontrol"> Components </span>  &gt; <span class="uicontrol"> Virtual Report Suites </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> The User Management interface, where you edit custom permissions groups. This allows VRS accounts to be added to a permissions group and could be used to create a group that only has access to virtual report suites (if the Admin wanted to deny access to the parent and only allow users access to specific segments). <p>( <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> User Management </span> </span>) </p> </li> 
    </ul> <p>Note:  When you use the Web Services API and attempt to save Feature settings against a VRS, an exception will be thrown. Features can only be set against a base report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Are virtual report suites supported in the SiteCatalyst 14 UI?</b> </td> 
   <td colname="col2"> <p>No, we do not expose virtual report suites in SiteCatalyst 14. They will not show up for selection in the Report Suite Selector and cannot be selected. We do, however, expose virtual report suites in the SiteCatalyst 14 Admin Console UI when editing a group. In this particular case virtual report suites need to be represented so they aren't accidentally removed from an already-existing group that may already have access to one/many virtual report suites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I checked "start new visit on launch." Why do I see visits still much higher than launches?</b> </td> 
   <td colname="col2"> <p> When the <span class="uicontrol"> start new visit on launch </span> option is checked, the timeout still applies. So, if a user is using the an app for ten minutes with a one minute break in between each action, a new visit starts on launch, then nine additional visits are created when the visit times out. To keep launches and visits as close as possible when <span class="uicontrol"> using the start new visit on launch </span> option, you should use a timeout that is longer than the session timeout set in the SDK . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I set "start new visit on launch" and set a longer timeout than my SDK. Why are my launches still much lower than visits?</b> </td> 
   <td colname="col2"> <p> If the timeout is higher than the value set in the SDK, it is very likely that your app is sending in hits while in the background and these hits are registering as new visits. Check for this by using the hit type dimension on the parent report suite to see if there are any background hits. </p> <p> <p>Note:  Background and foreground hits are only differentiated in version 4.13.6 and higher of the SDK. If you are on a lower version, all hits show as foreground. If you are on the correct version of the SDK, you should enabled the <span class="uicontrol"> Prevent background hits from starting a new visit </span> setting. </p> </p> <p> <p>Note:  If you have disabled legacy processing for background hits in the admin console, they will not show up in the parent report suite but will appear in the virtual report suite. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> What version of the SDK do I need to have to track background hits?</b> </td> 
   <td colname="col2"> <p> You must be on version 4.13.6 or higher of the SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>

