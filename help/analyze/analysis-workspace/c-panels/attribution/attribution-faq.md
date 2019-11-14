---
title: Attribution FAQ
description: Get answers to commonly asked questions around attribution.
---

# Attribution FAQ

**What is the "None" line item when using attribution?**

The 'None' line item is a catch-all that represents all conversions that happened without any touch points within the lookback window. Try including a longer time range in your reporting window.

**Why do I sometimes see dates outside of my reporting window when using attribution models?**

These extra dates are due to the visitor reporting lookback window. See [Data appearing outside reporting window](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) in the Analytics KB for more information. Adobe plans to filter out these extra rows in an upcoming release.

**Can I use a custom lookback window with my attribution models?**

Attribution models currently rely on either a visitor or visit lookback window. Either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of virtual report suites. See [Report time processing](../../../../components/vrs/vrs-report-time-processing.md) for more information.

**When should I use a visit vs. visitor attribution lookback?**

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor lookback is recommended. Creating a virtual report suite with a longer visit definition is also a potential solution.

**How do props and eVars compare when using attribution?**

Attribution is recalculated at report runtime, so there is no difference between a prop or eVar (or any other dimension) for the sake of attribution modeling. Props can persist using any lookback window or attribution model, and eVar allocation/expiration settings are ignored.

**Are attribution models available in other Analytics capabilities, such as Data Feeds or Data Warehouse?**

No. Attribution models use report time processing, which is only available in Analysis Workspace. See [Report time processing](../../../../components/vrs/vrs-report-time-processing.md) for more information.

**Are attribution models only available if I'm using a virtual report suite with report time processing enabled?**

Attribution models are available outside of virtual report suites. While they use report time processing on the backend, attribution models are available to both standard report suites and virtual report suites.

**What dimensions and metrics are not supported?**

The attribution panel supports all dimensions. Unsupported metrics include:

* Unique Visitors
* Visits
* Occurrences
* Page Views
* A4T metrics
* Time Spent metrics
* Bounces
* Bounce rate
* Entries
* Exits
* Pages Not Found
* Searches
* Single Page Visits
* Single Access

**How does attribution in Analysis Workspace differ from attribution in Data Workbench?**

Data Workbench incrementally offers:

* The ability to attribute across more visitor-level data sources, such as ad impressions and point of sale.
* Algorithmic modeling. Attribution in Analysis Workspace includes rules-based models only. See [Best fit modeling](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) in the Data Workbench user guide.
* Additional visualizations, such as latency tables. See [Latency tables](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) in the Data Workbench user guide.

**Does attribution work with classifications?**

Yes, classifications are fully supported.

**Does attribution work with data sources?**

Yes, most data sources are supported. Attribution is not possible with summary-level data sources because they do not tie to an Analytics visitor identifier. Transaction ID data sources are also supported, unless they are used in a virtual report suite with report time processing enabled.

**Does attribution work with the Advertising Analytics integration?**

Metadata dimensions, such as match type and keyword, work with attribution. However, metrics (including impressions, cost, clicks, average position, and average quality score) use summary-level data sources, and are therefore incompatible.
