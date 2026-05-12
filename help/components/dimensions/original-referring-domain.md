---
title: Original referring domain
description: The first referring domain a visitor was on before clicking through to your site.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
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
# Original referring domain

The 'Original referring domain' [dimension](overview.md) reports the first referring domain that a visitor clicked through to reach your site. Once it is set, it contains the same value for the entire lifetime of that visitor ID. This dimension is useful to understand which third-party sites originally drive traffic to your site.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

## Populate this dimension with data

This dimension requires configuration in both the Analytics interface and your implementation.

* Within your implementation, this dimension retrieves data from the [`r` query string](/help/implement/validate/query-parameters.md) in image requests. AppMeasurement collects this data using the JavaScript variable `document.referrer` in the browser. If you use an AppMeasurement library (such as through tags in Adobe Experience Platform), this dimension works out of the box. If you use a data collection method outside of AppMeasurement (such as through the API), make sure that you include the `r` query string parameter in image requests.
* Within the Analytics interface, you must configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Failure to configure internal URL filters can either include internal domains or prevent external domains from appearing.

Adobe persists original referring domain for a visitor's lifetime. If a visitor leaves and clicks through a link on a different domain at any time, the new value is not recorded. If you want to see new values, see [Referring domain](referring-domain.md).

## Dimension items

Dimension items include domains that visitors click through to your site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension item `"None"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark.

## Compare Referring domain to Original referring domain

Referring domain can change between visits. For example, a visitor arrives to your site through `google.com`, then a week later, arrives to your site through `twitter.com`. Eventually they make a purchase on your site. If using Referring domain as the dimension with last touch attribution, `twitter.com` gets credit for the purchase. If using Original referring domain as the dimension, `google.com` gets credit for the purchase regardless of attribution model.

Original referring domain never changes for the entire lifetime of a given visitor ID.
