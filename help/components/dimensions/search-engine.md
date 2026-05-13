---
title: Search engine
description: The search engine that the visitor used to reach your site.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
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
# Search engine

The 'Search engine' [dimension](overview.md) reports the search engines that visitors use to reach your site. A referrer must meet both of the following to classify as a search engine:

* The referring domain is recognized by Adobe as a valid search engine;
* A keyword query string parameter exists in the referring URL. The query string parameter can be blank (as is the case with several search engines due to privacy practices).

If you want to distinguish paid and natural search, [Paid search detection](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) is required. Multiple dimensions are available for search engines:

* **Search engine**: The search engine used to reach your site, regardless of if it is paid or natural.
* **Search engine - paid**: The search engine used to reach your site, which matched paid search detection.
* **Search engine - natural**: The search engine used to reach your site, which did not match paid search detection.

## Populate this dimension with data

This dimension references multiple lookup tables internal to Adobe. Each value is based on the [referrer](referrer.md) of the hit, which depends on [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Make sure that the referrer dimension and internal URL filters are configured correctly.

## Dimension items

Dimension items include search engines used to reach your site. Example values include `"Google"`, `"Microsoft Bing"`, and `"DuckDuckGo"`. The `"Unspecified"` dimension item is all non-search traffic.
