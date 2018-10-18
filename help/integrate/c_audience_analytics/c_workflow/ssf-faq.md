---
description: Frequently asked questions about features, functionality, and issues related to server-side forwarding.
seo-description: Frequently asked questions about features, functionality, and issues related to server-side forwarding.
seo-title: Server-Side Forwarding FAQ
title: Server-Side Forwarding FAQ
uuid: 1ffcd579-e314-448b-9277-945b42ee24c2
index: y
internal: n
snippet: y
---

# Server-Side Forwarding FAQ

Frequently asked questions about features, functionality, and issues related to server-side forwarding.

## Tracking Servers {#section_28E5BECC2034484AB9726E513F2CCFB7}

<table id="table_BFB77441225A49B1BCCE80F8CBF5C8E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if I'm currently using the legacy, tracking-server-based server side forwarding?</b> </p> </td> 
   <td colname="col2"> <p>The legacy tracking-server-based server side forwarding method will continue to forward data from Analytics to Audience Manager, however if you wish to send Audience Manager segments into Analytics, the new report-suite-based server side forwarding is required. Additionally, there is no harm in enabling a report suite for server-side forwarding on top of your tracking server configuration - the new report suite server-side forwarding setting will be used whenever there is a conflict. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Should I migrate my legacy tracking-server-based server side forwarding to the new report-suite-based server side forwarding?</b> </p> </td> 
   <td colname="col2"> <p>We will continue to support tracking-server-based server side forwarding for the foreseeable future. However, if you want to take advantage of the integration from Audience Manager to Analytics (segment sharing to Analytics), then you'll need to enable the new report-suite-based server side forwarding for all applicable report suites. There is no urgent reason to disable the legacy tracking-server-based server side forwarding. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

<table id="table_695CEADF0ACF4EB0903AE85C8D608C86"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if I have multi-suite tagging on my site? Will server-side forwarding double my server calls to Audience Manager?</b> </p> </td> 
   <td colname="col2"> <p>No, a hit that is forwarded from Analytics to Audience Manager will only be forwarded once to Audience Manager regardless of the number of report suites in the hit. If you have corresponding data sources in Audience Manager for each of the report suites in the hit, each will be populated appropriately from that single hit. </p> <p>Keep in mind that if you currently use client-side data collection (DIL) and you enable server-side forwarding without installing the Audience Management Module, you will double your server calls to Audience Manager regardless of the number of report suites you have in your Analytics hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if I have multi-suite tagged report suites that are mapped to separate Experience Cloud organizations?</b> </p> </td> 
   <td colname="col2"> <p>You should never send data from a single Analytics hit to two report suites that belong to separate Experience Cloud organizations, but if this does occur, we will only forward the hit to the organization matching the Experience Cloud ID Service setup on the page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if I have multi-suite tagging and only one of my report suites is mapped to my Experience Cloud organization and the other is not?</b> </p> </td> 
   <td colname="col2"> <p>We will forward the hit to the corresponding data collection server for the Experience Cloud organization on your mapped report suite, however since the non-mapped report suite will not have an associated data source in Audience Manager, no data will be recorded for the un-mapped report suite in Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if I have a report suite that is mapped to multiple organizations?</b> </p> </td> 
   <td colname="col2"> <p>Analytics will consider this report suite as unmapped and will not allow server side forwarding to be enabled for this report suite. Contact customer care to resolve this mapping issue. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Will the report-suite-based server side forwarding method be slower than tracking-server-based server side forwarding?</b> </p> </td> 
   <td colname="col2"> <p>No, the response time will be the same. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: What if we have two Experience Cloud organizations (or AAM instances) and want to share data between both organizations? Can I server side forward a single Analytics hit to multiple organizations?</b> </p> </td> 
   <td colname="col2"> <p>No. If you need to share data collected under one Experience Cloud organization to another Experience Cloud organization, we recommend sending any applicable audiences from one Audience Manager instance to another using the audience marketplace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Will server-side forwarding result in any additional billing in Audience Manager or Analytics?</b> </p> </td> 
   <td colname="col2"> <p>In Analytics, no additional billing will occur. In Audience Manager, forwarded hits are treated like any other hits and are billed. </p> <p>This is why it is important not to have DIL and server-side forwarding enabled at the same time, which could cause double-billing as well as data duplication. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Server-Side Forwarding](ssf.md#concept_9563FCADF29748928E770EC5221B2685)
