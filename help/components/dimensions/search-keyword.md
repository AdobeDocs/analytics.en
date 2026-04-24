---
title: Search keyword
description: The search keyword that the visitor used to reach your site.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Search keyword

The 'Search keyword' [dimension](overview.md) reports the search keywords that visitors use to reach your site.

>[!IMPORTANT]
>
>Most search engines no longer pass the search keyword due to increasing privacy practices. Hits where Adobe recognizes a search engine but is missing a keyword groups under the dimension item `"Keyword unavailable"`.

A referrer must meet both of the following to classify as a search keyword:

* The referring domain is recognized by Adobe as a valid [Search engine](search-engine.md);
* A keyword query string parameter exists in the referring URL. If the keyword query string exists but does not contain a value, it groups under the dimension item `"Keyword unavailable"`.

If you want to distinguish paid and natural search, [Paid search detection](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) is required. Multiple dimensions are available for search keywords:

* **Search keyword**: The search keyword used to reach your site, regardless of if it is paid or natural.
* **Search keyword - paid**: The search keyword used to reach your site, which matched paid search detection.
* **Search keyword - natural**: The search keyword used to reach your site, which did not match paid search detection.

## Populate this dimension with data

This dimension references multiple lookup tables internal to Adobe. Each value is based on the [referrer](referrer.md) of the hit, which depends on [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Make sure that the referrer dimension and internal URL filters are configured correctly.

## Dimension items

Dimension items include search keywords used to reach your site. The `"Unspecified"` dimension item is all non-search traffic.
