---
description: null
keywords: DFA
seo-description: null
seo-title: Update your DFA Query-String Parameter
solution: Analytics
title: Update your DFA Query-String Parameter
topic: Data connectors
uuid: adf585ac-84ff-44c1-a48d-b072726c8494
index: y
internal: n
snippet: y
---

# Update your DFA Query-String Parameter{#update-your-dfa-query-string-parameter}

If you have already been tracking Ad campaigns with Adobe Analytics prior to the DFA integration, it is possible that all campaigns (email, search, or banner) use the same query string parameter to identify the referring campaign ID on the landing page.

To understand when to request view-through and click-through data from DFA data for your DFA Ad campaigns, Data Connectors needs to identify when a visitor has clicked on a DFA campaign banner ad. To make this possible, you must add a differentiated query-string parameter to the DFA Ad campaign’s landing page URL so Data Connectors can distinguish between DFA Ad campaign pages and other ad campaign pages that you might have on your Web site. The `dfa_overrideParam` in the JavaScript plug-in (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) used for DFA.

>[!CAUTION]
>
>Although the Campaign variable can be used for other campaigns, do not use it for DFA campaigns. If you set the Campaign variable to a DFA campaign landing page, Adobe cannot tie impressions and clicks to DFA campaign click-throughs. Once per visit, Adobe collection servers check DFA servers for a previous click- or view-through. Because of this, include the DFA plug-in code (see [Update Your Web Site's Data Collection Code](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) only on common landing pages to avoid unnecessary redirects that can slow page-load times, particularly for users with slower Internet connections.

