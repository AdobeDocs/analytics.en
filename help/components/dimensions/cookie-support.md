---
title: Cookie support
description: Determines if the browser supports cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Cookie Support

The 'Cookie support' [dimension](overview.md) reports if the browser supports cookies for a given hit. It is useful to determine the ratio of visitors who use browsers that support cookies, and those who intentionally disable them.

## Populate this dimension with data

This dimension collects data from the [`k` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement tries to set a cookie named `s_cc`, then detects if the cookie exists. The result is the query string parameter value `Y` (if the browser supports and has cookies enabled) or `N` (if the browser has cookies disabled). If you use AppMeasurement (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `k` query string parameter on each hit with the value `Y` or `N`.

## Dimension items

Dimension items include `Enabled`, `Disabled`, and `Unknown`.

* **`Enabled`**: The browser supports cookies, and has them enabled.
* **`Disabled`**: The browser does not support cookies, or the visitor disabled them.
* **`Unknown`**: AppMeasurement could not determine cookie support. The `k` query string was not present in the image request.
