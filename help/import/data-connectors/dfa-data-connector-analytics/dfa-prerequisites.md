---
description: null
keywords: DFA
seo-description: null
seo-title: Prerequisites
solution: Analytics
title: Prerequisites
topic: Data connectors
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
---

# Prerequisites{#prerequisites}

Before starting the Adobe Data Connectors integration for DFA, do the following:

* Decide whether to integrate against version 1.5 of the integration, or to wait for version 2.0. This decision is dependent upon which features are utilized in your DFA account, and the time frame in which you want to integrate.  
* Decide how DFA Advertisers will map to Adobe Analytics report suites. For example, if you have multiple DFA Advertisers and multiple report suites, you will need to decide which Advertisers pair with which report suites. 
* Implement Adobe data collection code on all the pages you want to track, using version H.22 or later of the data collection code. 
* Know the Advertiser ID for a DFA account that is part of the Floodlight Configuration you want to integrate. The integration automatically imports all of the Advertisers that lie within the Floodlight Configuration. 
* Know your DFA account User Name and Password. 
* Associate each DFA Advertiser to only one Adobe Analytics report suite. Tagging to multiple report suites is not supported with the default Genesis integration for DFA. 
* Add a click-through query string parameter to the landing page for each DFA Placement which will be part of the integration. This query string parameter is necessary to properly count Click-throughs. 
* Configure your DFA Placements so that they do not redirect visitors through multiple domains. For example, a Placement should not direct respondents to a micro-site hosted under www.xyz.com if the micro-site then redirects them to another site, www.fgh.com. If the campaign response spans multiple domains, click-through and view-through data can be inflated and misleading. 
* Identify a custom variable in Reports & Analytics to hold your campaign information. 
* Identify a Reports & Analytics eVar to store DFA view-through information. Use this eVar only for this DFA integration. 
* Identify the Reports & Analytics events where you want to store Impressions and Click data. You might want to rename these events appropriately. 
* (Optional) Identify the Reports & Analytics events which will store DFA Cost data. You might want to rename these events appropriately. 
* (Optional) Identify a Reports & Analytics Custom Variable and Success Event which will store DFA errors and timeouts. These variables help to diagnose problems that might arise with the integration. 
* (Optional) Create a special Email account for receiving information and notifications related to the Data Connectors integration for DFA.

