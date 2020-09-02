---
title: Attribution FAQ
description: Get answers to commonly asked questions around attribution.
---

# Attribution FAQ

**What is the "None" line item when using attribution?**

The 'None' line item is a catch-all item that represents all conversions that happened without any touch points within the lookback window. To reduce the number of conversions attributed to the 'None' line item, try using a a Custom Lookback Window with a longer lookback period.

**Why do I sometimes see dates outside of my reporting window when using attribution models?**

These extra dates are due to the visitor reporting lookback window. See [Data appearing outside reporting window](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) in the Analytics KB for more information.

**When should I use a visit, visitor, or custom attribution lookback?**

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor or custom lookback is recommended. For longer conversion cycles, custom lookback windows are best as they are the only type that can pull in data from prior to the reporting window

**How do props and eVars compare when using attribution?**

Attribution is recalculated at report runtime, so there is no difference between a prop or eVar (or any other dimension) for the sake of attribution modeling. Props can persist using any lookback window or attribution model, and eVar allocation/expiration settings are ignored.

**Are attribution models available in other Analytics capabilities, such as Data Feeds or Data Warehouse?**

No. Attribution models use report time processing, which is only available in Analysis Workspace. See [Report time processing](/help/components/vrs/vrs-report-time-processing.md) for more information.

**Are attribution models only available if I'm using a virtual report suite with report time processing enabled?**

Attribution models are available outside of virtual report suites. While they use report time processing on the backend, attribution models are available to both standard report suites and virtual report suites.

**What dimensions and metrics are not supported?**

The attribution panel supports all dimensions. Unsupported metrics include:

* All calculated metrics
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

**Does attribution work with classifications?**

Yes, classifications are fully supported.

**Does attribution work with data sources?**

Yes, most data sources are supported. Attribution is not possible with summary-level data sources because they do not tie to an Analytics visitor identifier. Transaction ID data sources are also supported, unless they are used in a virtual report suite with report time processing enabled.

**Does attribution work with the Advertising Analytics integration?**

Metadata dimensions, such as match type and keyword, work with attribution. However, metrics (including impressions, cost, clicks, average position, and average quality score) use summary-level data sources, and are therefore incompatible.

**How does attribution work with marketing channels?**

When marketing channels were first introduced, they came with only first and last touch dimensions. Explicit first/last touch dimensions are no longer needed with the current version of attribution. Adobe provides generic 'Marketing Channel' and 'Marketing Channel Detail' dimensions so you can use them with your desired attribution model. These generic dimensions behave identically to Last Touch Channel dimensions, but are labeled differently to prevent confusion when using marketing channels with a different attribution model.

Since marketing channel dimensions depend on a traditional visit definition (as defined by their processing rules), their visit definition cannot be changed using virtual report suites.

**How does attribution work with multi-value variables, such as list vars?**

Some dimensions in Analytics can contain multiple values on a single hit. Common examples include list vars and the products variable.

When attribution is applied to multi-value hits, all values in the same hit get the same credit. Since many values can receive this credit, the report total can be different than if you summed each individual line item. The report total is deduplicated, while each individual dimension item gets proper credit.

**How does attribution work with segmentation?**

Attribution always runs before segmentation, and segmentation runs before report filters are applied. This concept also applies to virtual report suites using segments.

For example, if you create a VRS with a "Display Hits" segment applied, you could see other channels in a table using some attribution models.

![Display-only virtual report suite](assets/vrs-aiq-example.png)

>[!NOTE]
>
>If a segment suppresses hits containing your metric, those metric instances will not be attributed to any dimension. However, a similar report filter will simply hide some dimension items, without any impact on metrics processed per the attribution model. As a result, a segment can return lower values than a filter with a comparable definition.
