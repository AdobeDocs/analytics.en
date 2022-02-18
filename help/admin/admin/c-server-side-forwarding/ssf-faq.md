---
description: Frequently asked questions about features, functionality, and issues related to server-side forwarding.
title: Server-side forwarding FAQ
feature: Server-Side Forwarding
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
---
# Server-side forwarding FAQ

Frequently asked questions about features, functionality, and issues related to server-side forwarding.

## Tracking Servers {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Question | Answer |
|--- |--- |
|Q: What if I'm currently using the legacy, tracking server based server side forwarding?|The legacy tracking server based server side forwarding method will continue to forward data from Analytics to Audience Manager, however if you wish to send Audience Manager segments into Analytics, the new report suite based server side forwarding is required. Additionally, there is no harm in enabling a report suite for server side forwarding on top of your tracking server configuration - the new report suite server-side forwarding setting will be used whenever there is a conflict.|
|Q: Should I migrate my legacy tracking server based server side forwarding to the new report suite based server side forwarding?|We will continue to support the tracking server based server side forwarding for the foreseeable future, however if you want to take advantage of the integration from Audience Manager to Analytics (segment sharing to Analytics), then you'll need to enable the new report suite based server side forwarding for all applicable report suites. There is no urgent reason to disable the legacy tracking server based server side forwarding however.|

## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

| Question | Answer |
|--- |--- |
|Q: What if I have multi-suite tagging on my site? Will server-side forwarding double my server calls to Audience Manager?|No, a hit that is forwarded from Analytics to Audience Manager will only be forwarded once to Audience Manager regardless of the number of report suites in the hit. If you have corresponding data sources in Audience Manager for each of the report suites in the hit, each will be populated appropriately from that single hit.  Keep in mind however, that if you currently use client-side data collection (DIL) and you enable server-side forwarding without installing the Audience Management Module, you will double your server calls to Audience Manager regardless of the number of report suites you have in your Analytics hit.|
|Q: What if I have multi-suite tagged report suites that are mapped to separate Experience Cloud Orgs?|You should never send data from a single Analytics hit to two report suites that belong to separate Experience Cloud Orgs, but if this does occur, we will only forward the hit to the Experience Cloud Org matching the Identity Service setup on the page.|
|Q: What if I have multi-suite tagging and only one of my report suites is mapped to my Experience Cloud Org and the other is not?|We will forward the hit to the corresponding data collection server for the Experience Cloud Org on your mapped report suite, however since the non-mapped report suite will not have an associated data source in Audience Manager, no data will be recorded for the un-mapped report suite in Audience Manager.|
|Q: What if I have a report suite that is mapped to multiple Experience Cloud Orgs?|Analytics will consider this report suite as unmapped and will not allow server side forwarding to be enabled for this report suite. Contact customer care to resolve this mapping issue.|
|Q: Will the report suite based server side forwarding method be slower than the tracking server based server side forwarding?|No, the response time will be the same.|
|Q: What if we have two Experience Cloud Orgs (or AAM instances) and want to share data between both Experience Cloud Orgs? Can I server side forward a single Analytics hit to multiple Experience Cloud Orgs?|No. If you need to share data collected under one Experience Cloud Org to another Experience Cloud Org, we recommend sending any applicable audiences from one Audience Manager instance to another using the audience marketplace.|
|Q: Will server-side forwarding result in any additional billing in Audience Manager or Analytics?|In Analytics, no additional billing will occur. In Audience Manager, forwarded hits are treated like any other hits and are billed.  This is why it is important not to have DIL and server-side forwarding enabled at the same time, which could cause double-billing as well as data duplication.|

>[!MORELIKETHIS]
>
>* [Server-Side Forwarding](/help/admin/admin/c-server-side-forwarding/ssf.md)
