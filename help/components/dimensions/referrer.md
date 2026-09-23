---
title: Referrer
description: The URL a visitor was at before clicking through to your site.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
# Referrer

The 'Referrer' [dimension](overview.md) reports which URLs visitors were on when clicking through to reach your site. This dimension is useful to understand which specific URLs drive the most traffic to your site. A link must exist on the external URL and a visitor must click it in order for the dimension item to show up.

>[!IMPORTANT]
>
>You must configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) to use this dimension. Failure to configure internal URL filters can either include internal URLs or prevent external URLs from appearing.

The same report can show different results between Analysis Workspace and Data Warehouse. Analysis Workspace reports the referrer for each individual page, excluding values that match internal URL filters. Data Warehouse reports only the first referrer of the visit, and ignores internal URL filters.

## Populate this dimension with data

AppMeasurement automatically collects the referrer from the browser's `document.referrer` value. You can override the collected value using the [`referrer`](/help/implement/vars/page-vars/referrer.md) variable. You must also configure your report suite's [Internal URL filters](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md); failure to do so can either include internal URLs or prevent external URLs from appearing.

| Property | Value |
| --- | --- |
| **AppMeasurement variable** | [`referrer`](/help/implement/vars/page-vars/referrer.md) |
| **Web SDK / XDM field** | [`web.webReferrer.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/web-information) |
| **Query parameter** | [`r`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML tag** | [`<referrer>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Byte limit** | 255 bytes |
| **Persistence** | N/A |

## Dimension items

Dimension items include URLs that visitors click through to your site. If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. This dimension item means that there was no referrer value, such as if the visitor manually typed the browser address into the address bar, or clicked a bookmark. The `"Typed/Bookmarked"` dimension item also appears for redirects that don't accommodate Analytics. See [Redirects and aliases](/help/technotes/redirects.md) in the Technotes user guide.

### Dimension items containing `googleusercontent.com`

Users can see dimension items with the domain `googleusercontent.com`.

* **Cached pages**: Google's spiders constantly crawl the web and store copies of pages in case they are taken offline. These cached pages are available next to most search results by clicking the "Cached" link. When a user clicks this link and views the content that Google cached, `webcache.googleusercontent.com` is a typical dimension item.
* **Translated pages**: Google offers a robust and convenient translation service. When viewing a site using this service, it originates from `translate.googleusercontent.com`. This dimension item appears if the user clicks a link to return to the original content.
