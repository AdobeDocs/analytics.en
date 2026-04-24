---
title: Pages not found (dimensions)
description: URLs that returned an error on your site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Pages not found

*This help page describes how 'Pages not found' works as a [dimension](overview.md). See the [Pages not found](../metrics/pages-not-found.md) metric page for information on how it works as a metric.*

The 'Pages not found' dimension shows URLs that contained an error. This dimension is useful when you want to lower the number of errors that visitors get on your site.

* You can use this dimension in a [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) to see which pages visitors click through to reach the error. You can then work with development teams in your organization to fix the link on each page.
* You can use this dimension with the ['Referrer'](referrer.md) dimension to see where visitors arrive to your site from external links. You can then either implement redirects to the desired location, or work with the third party to get the link fixed.

## Populate this dimension with data

This dimension retrieves data from the [`pageType` and `g` query strings](/help/implement/validate/query-parameters.md) in image requests. If the `pageType` query string equals `errorPage`, the `g` query string (page URL) is recorded. AppMeasurement collects this data using the [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. If the `pageType` variable is not defined or set to anything other than `errorPage`, no data for this dimension is collected.

## Dimension items

Dimension items include the URLs of pages on your site where an error occurred.
