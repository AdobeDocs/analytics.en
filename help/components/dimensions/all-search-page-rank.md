---
title: All search page rank
description: Determine which page on a search engine a visitor clicked through to your site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
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
# All search page rank

The 'All search page rank' [dimension](overview.md) provides insight on which page of search results a visitor clicked through to your site. For example, if your site appears on the second page of a search engine's search results, the dimension item for this variable is "Search Page 2".

## Populate this dimension with data

Getting this dimension to work only requires that your report suite have [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) set up correctly. AppMeasurement automatically populates this dimension without any implementation code changes.

## Dimension items

If a visitor clicks through to your site from a search engine, this dimension's value is "Search Page" followed by the page number they clicked through on. If a hit does not originate from a search engine, this dimension's value is "Unspecified".
