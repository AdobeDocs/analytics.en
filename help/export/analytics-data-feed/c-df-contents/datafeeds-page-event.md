---
description: Lookup table to determine the type of a hit based on the page_event value.
keywords: Data Feed;page;event;page_event;post_page_event
seo-description: Lookup table to determine the type of a hit based on the page_event value.
seo-title: Page Event Lookup
solution: Analytics
title: Page Event Lookup
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
---

# Page Event Lookup

Lookup table to determine the type of a hit based on the page_event value.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hit type </th> 
   <th colname="col02" class="entry"> page_event value </th> 
   <th colname="col2" class="entry"> post_page_event value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page views </td> 
   <td colname="col02"> same as post </td> 
   <td colname="col2"> <p>0 for all page views ( <span class="codeph"> s.t() </span> calls) </p> <p>0 for <span class="codeph"> trackState </span> calls from the mobile SDKs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Link tracking </td> 
   <td colname="col02"> <p>10 for "other link" </p> <p>10 for <span class="codeph"> trackAction </span> and lifecycle calls from the Mobile SDKs. </p> <p>11 for "download link" </p> <p>12 for "external or exit link" </p> </td> 
   <td colname="col2"> <p>100 for "other link" </p> <p>100 for <span class="codeph"> trackAction </span> and lifecycle calls from the Mobile SDKs. </p> <p>101 for "download link" </p> <p>102 for "external or exit link" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Milestone Video </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 - Media start event </p> <p>32 - Media update only event (doesn’t perform any eVar or any other variable processing) </p> <p>33 - Media + other variable update event (includes eVar and other variable processing) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 - Media start event </p> <p>77 - Media update only event (doesn't perform any eVar or any other variable processing) </p> <p>78 - Media + other variable update event (includes eVar and other variable processing) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Heartbeat Video </p> </td> 
   <td colname="col02"> same as post </td> 
   <td colname="col2"> <p> 50 = (non-Primetime) Media Stream Start </p> <p> 51 = (non-Primetime) Media Stream Close (Complete/Finish) </p> <p> 52 = (non-Primetime) Media Stream Scrubbing </p> <p> 53 = (non-Primetime) Media Stream Keep Alive </p> <p> 54 = (non-Primetime) Media Stream Ad Start </p> <p> 55 = (non-Primetime) Media Stream Ad Close (Complete/Finish) </p> <p> 56 = (non-Primetime) Media Stream Ad Scrubbing </p> <p> 60 = Primetime Media Stream Start </p> <p> 61 = Primetime Media Stream Close (Complete/Finish) </p> <p> 62 = Primetime Media Stream Scrubbing </p> <p> 63 = Primetime Media Stream Keep Alive </p> <p> 64 = Primetime Media Stream Ad Start </p> <p> 65 = Primetime Media Stream Ad Close (Complete/Finish) </p> <p> 66 = Primetime Media Stream Ad Scrubbing </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Survey </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics for Target </td> 
   <td colname="col02"> 70 - Indicates a hit that includes Target Activity data. This is 70 for hits that are and are not associated with an Analytics call. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

