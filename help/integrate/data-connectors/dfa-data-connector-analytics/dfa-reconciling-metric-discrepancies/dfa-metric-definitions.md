---
description: Adobe uses the following terms when talking about metrics related to the DFA integration 
keywords: DFA
seo-description: Adobe uses the following terms when talking about metrics related to the DFA integration 
seo-title: Metric Definitions
solution: Analytics
title: Metric Definitions
topic: Data connectors
uuid: 062f6863-3daa-4e8a-b6ea-84279d49c388
index: y
internal: n
snippet: y
---

# Metric Definitions{#metric-definitions}

Adobe uses the following terms when talking about metrics related to the DFA integration:

 **Impressions**: Impressions refer to the number of times an ad was viewed. Impressions are reported on an ad-by-ad basis, but can also be aggregated into ad groups or other multi-ad groupings. The impressions metric in Analytics is imported from DFA via a nightly data sources import.

**Clicks**: Clicks refer to the number of times an ad was clicked, as report by DFA. Clicks are registered on the DFA redirect page prior to the visitor landing on the customer's website. Like impressions, the clicks metric in Analytics is imported from DFA via a nightly data sources import.

**Click-Throughs**: Click-Throughs refer to the number of times the user arrived to the landing page, after clicking on an ad. This metric can be subtly different from Clicks.

**View-Throughs**: View-Throughs refer to the number of times a visitor came to the customer's Web site after viewing an ad, but having NOT clicked the ad. The visitor must come to the site within the view-through window, which by default, is set to 30 days. The impression must have happened more recently than the last click. View-throughs are registered once per campaign, per visit and are counted when the integration populates the view-through eVar with the DFA campaign ID, and the view-through event is set. 
