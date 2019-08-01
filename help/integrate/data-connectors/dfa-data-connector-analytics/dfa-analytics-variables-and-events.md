---
description: The Data Connectors integration for DFA uses Analytics variables to track DFA campaign results.
keywords: DFA
seo-description: The Data Connectors integration for DFA uses Analytics variables to track DFA campaign results.
seo-title: Analytics Variables and Events
solution: Analytics
title: Analytics Variables and Events
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
index: y
internal: n
snippet: y
---

# Analytics Variables and Events{#analytics-variables-and-events}

The Data Connectors integration for DFA uses Analytics variables to track DFA campaign results.

Other than the campaign variable, you can use the Analytics Events and eVars that make sense to you. Once you have identified the Event and eVars to use with this DFA integration, use the Analytics Admin Console to enable them. The integration variables must be enabled before activating the DFA integration. The following table describes the Analytics variables needed for the DFA integration. 

|  Variable  | Friendly Name  | Population Method  | Description  |
|---|---|---|---|
|  s.campaign or eVar  | Ad Tracking Code  | Automatically populated by Data Connector for DFA campaigns.  | Tracks click-through conversions for all campaigns.  |
|  eVar&#42;  | View-Through  | Automatically populated through VISTA and DFA for DFA campaigns.  |Tracks view-through data for DFA IDs. This eVar should have the same expiration as the *`s.campaign`* variable. Must be the same conversion variable as identified in the Variable Provider ID (See [Update Your Website’s Data Collection Code](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). Make sure the eVar has full subrelations enabled. The cost for enabling this feature is part of the Data Connectors integration fee  |
|  eVar&#42;  | DFA Query Errors  | (Optional) Populated through JavaScript collection code.  |Contains one of several error codes returned from DFA (see the table in [Configuring the Integration](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858) for a listing of these error codes)  |
|  event&#42;  | View-Through Count  | Automatically populated by Data Connector for DFA campaigns.  | Captures the number of times users viewed an ad, did not click-through, but arrived at your site.  |
|  event&#42;  | Impressions  | Automatically populated through a data feed from DFA.  | Tracks the number of time a specific DFA ad was served.  |
|  event&#42;  | Clicks  | Automatically populated through a data feed from DFA.  |Tracks the number of times users clicked a specific DFA banner ad. This metric can yield different numbers compared to the native Analytics click-throughs metric for one of several reasons. See [Reconciling Metric Discrepancies](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) for more information.  |
|  event&#42;  | DFA Timeouts  | (Optional) Populated through JavaScript collection code.  |Counts the number of times DFA fails to respond before the *`s.maxDelay`* time out. This can help you determine if there is a DFA implementation issue.  |
|  event&#42;  | DFA Media Cost  | Automatically populated through a data feed from DFA.  | Contains the media cost metrics that have been input in the DFA interface. This feature must be enabled on the DFA side in order for these metrics to appear.  |

&#42;Select an unused eVar or Custom Event. 
