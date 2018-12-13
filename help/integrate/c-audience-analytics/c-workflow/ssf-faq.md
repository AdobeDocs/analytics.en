---
description: Frequently asked questions about features, functionality, and issues related to server-side forwarding.
seo-description: Frequently asked questions about features, functionality, and issues related to server-side forwarding.
seo-title: Server-side forwarding FAQ
title: Server-side forwarding FAQ
uuid: 7d6ce34c-a437-485a-8c0b-45225561f6ab
index: y
internal: n
snippet: y
---

# Server-side forwarding FAQ

Frequently asked questions about features, functionality, and issues related to server-side forwarding.

Contents:

<ul class="simplelist"> 
 <li><a href="../../../integrate/c-audience-analytics/c-workflow/ssf-faq.md#section_28E5BECC2034484AB9726E513F2CCFB7" format="dita" scope="local"> Tracking Servers</a> </li> 
 <li><a href="../../../integrate/c-audience-analytics/c-workflow/ssf-faq.md#section_71391BA901AC47B9A2286281644FF281" format="dita" scope="local"> Tagging and Reporting</a> </li> 
</ul>

## Tracking Servers {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Question | Answer |
|--- |--- |
|Q: What if I'm currently using the legacy (tracking-server-based) server-side forwarding?|The legacy tracking-server-based server-side forwarding method will continue to forward data from Analytics to Audience Manager, however if you wish to send Audience Manager segments into Analytics, the new report-suite-based server-side forwarding is required. Additionally, there is no harm in enabling a report suite for server-side forwarding on top of your tracking server configuration - the new report suite server-side forwarding setting will be used whenever there is a conflict.|
|Q: Should I migrate my legacy tracking-server-based server-side forwarding to the new report-suite-based server-side forwarding?|We will continue to support the tracking-server-based server-side forwarding for the foreseeable future. However, if you want to take advantage of the integration from Audience Manager to Analytics (segment sharing to Analytics), then you need to enable the new report-suite-based server-side forwarding for all applicable report suites. There is no urgent reason to immediately disable the legacy tracking-server-based server-side forwarding.|


## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

| Question | Answer |
|--- |--- |
|Q: What if I have multi-suite tagging on my site? Will server-side forwarding double my server calls to Audience Manager?|No, a hit that is forwarded from Analytics to Audience Manager will only be forwarded once to Audience Manager, regardless of the number of report suites in the hit. If you have corresponding data sources in Audience Manager for each of the report suites in the hit, each will be populated appropriately from that single hit.  Keep in mind, however, that if you currently use client-side data collection (DIL) and you enable server-side forwarding without installing the Audience Management Module, you will double your server calls to Audience Manager regardless of the number of report suites you have in your Analytics hit.|
|Q: What if I have multi-suite tagged report suites that are mapped to separate Experience Cloud organizations?|You should never send data from a single Analytics hit to two report suites that belong to separate Experience Cloud organizations, but if this does occur, we will only forward the hit to the Experience Cloud organization matching the Experience Cloud ID Service setup on the page.|
|Q: What if I have multi-suite tagging and only one of my report suites is mapped to my Experience Cloud organizations and the other is not?|We will forward the hit to the corresponding data collection server for the Experience Cloud organization on your mapped report suite, however since the non-mapped report suite will not have an associated data source in Audience Manager, no data will be recorded for the un-mapped report suite in Audience Manager.|
|Q: What if I have a report suite that is mapped to multiple Experience Cloud organizations?|Analytics considers this report suite unmapped and will not allow server-side forwarding to be enabled for this report suite. Contact Adobe Customer Care to resolve this mapping issue.|
|Q: Is report-suite-based server-side forwarding slower than tracking-server-based server-side forwarding?|No, the response time is the same.|
|Q: What if we have two Experience Cloud organizations (or AAM instances) and want to share data between both? Can I server side forward a single Analytics hit to multiple Experience Cloud organizations?|No. If you need to share data collected under one Experience Cloud organization to another Experience Cloud organization, we recommend sending any applicable audiences from one Audience Manager instance to another using the audience marketplace.|
|Q: Will server-side forwarding result in any additional billing in Audience Manager or Analytics?|In Analytics, no additional billing will occur. In Audience Manager, forwarded hits are treated like any other hits and are billed.  This is why it is important not to have DIL and server-side forwarding enabled at the same time, which could cause double billing as well as data duplication.|


>[!MORE_LIKE_THIS]
>
>* [Server-Side Forwarding](ssf.md#concept_9563FCADF29748928E770EC5221B2685)
