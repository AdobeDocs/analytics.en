---
title: Automatically mapped Analytics variables in Adobe Experience Edge
description: View which XDM fields that Edge automatically maps to Analytics variables.
---

# Automatically mapped Analytics variables in Adobe Experience Edge

The following tables shows the variables that Adobe Experience Platform Edge Network automatically maps into Adobe Analytics. If you use these XDM Field Paths, no additional configuration is necessary to send data to Adobe Analytics.

Custom Analytics variable, such as [eVars]() or [props]() require [manual mapping](manual-mapping.md).

Detailed information about Adobe Analytics data collection query parameters can be found in the [Analytics Implementation Guide](https://experienceleague.adobe.com/docs/analytics/implementation/validate/query-parameters.html).

| XDM Field Path  | Analytics dimension and description |
| --- | --- |
| `application.id` | The [mobile dimension](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) App ID. Uses context data `c.a.appid`. |
| `application.launches.value` | The [mobile metric](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) Launches. Uses context data `c.a.launches`. |
| `commerce.checkouts.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Checkouts](../../components/metrics/checkouts.md) metric. |
| `commerce.checkouts.value` | Increments the [Checkouts](../../components/metrics/checkouts.md) metric by the desired amount. |
| `commerce.order.currencyCode` | Sets the [currencyCode](../vars/config-vars/currencycode.md) configuration variable. |
| `commerce.order.purchaseID` | Sets the [purchaseID](../vars/page-vars/purchaseid.md) page variable. |
| `commerce.productListAdds.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Additions](../../components/metrics/cart-additions.md) metric. |
| `commerce.productListAdds.value` | Increments the [Cart Additions](../../components/metrics/cart-additions.md) metric by the desired amount. |
| `commerce.productListOpens.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Carts](../../components/metrics/carts.md) metric. |
| `commerce.productListOpens.value` | Increments the [Carts](../../components/metrics/carts.md) metric by the desired amount. |
| `commerce.productListRemovals.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Removals](../../components/metrics/cart-removals.md) metric. |
| `commerce.productListRemovals.value` | Increments the [Cart Removals](../../components/metrics/cart-removals.md) metric by the desired amount. |
| `commerce.productListViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Views](../../components/metrics/cart-views.md) metric. |
| `commerce.productListViews.value` | Increments the [Cart Views](../../components/metrics/cart-views.md) metric by the desired amount. |
| `commerce.productViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Product Views](../../components/metrics/product-views.md) metric. |
| `commerce.productViews.value` | Increments the [Product Views](../../components/metrics/product-views.md) metric by the desired amount. |
| `commerce.purchases.value` | Increments the [Orders](../../components/metrics/orders.md) metric by the desired amount. |
| `device.colorDepth` | Sets the [Color Depth](../../components/dimensions/color-depth.md) dimension. |
| `device.screenHeight` | Contributes to setting the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. Make sure that you also set the XDM field `device.screenWidth`. |
| `device.screenWidth` | Contributes to setting the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. Make sure that you also set the XDM field `device.screenHeight`. |
| `environment.browserDetails.acceptLanguage` | Helps set the [Language](../../components/dimensions/language.md) dimension. |
| `environment.browserDetails.cookiesEnabled` | Sets the [Cookie Support](../../components/dimensions/cookie-support.md) dimension. Valid values include `Y` (the browser accepts cookies) and `N` (the browser rejects cookies). |
| `environment.browserDetails.javaEnabled` | Sets the [Java enabled](../../components/dimensions/java-enabled.md) dimension. Valid values include `Y` (Java is enabled) and `N` (Java is disabled). |
<!--| `environment.browserDetails.javaScriptVersion` | I don't think this dimension exists in Analytics anymore. | -->
| `environment.browserDetails.userAgent` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `User-Agent` HTTP request header. You can [manually map](manual-mapping.md) it to an eVar if you would like to use it in reports. |
| `environment.browserDetails.viewportHeight` | Sets the [Browser Height](../../components/dimensions/browser-height.md) dimension. |
| `environment.browserDetails.viewportWidth` | Sets the [Browser Width](../../components/dimensions/browser-width.md) dimension. |
| `environment.connectionType` | Helps set the [Connection type](../../components/dimensions/connection-type.md) dimension. |
| `environment.ipV4` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `X-Forwarded-For` HTTP header. |
| `identityMap.ECID[0].id` | The [Adobe Experience Cloud Identity Service ID](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| `marketing.trackingCode` | Sets the [Tracking Code](../../components/dimensions/tracking-code.md) dimension. |


| marketing.trackingCode | v0 | AppMeasurement query parameter CAMPAIGN mapping. |
| media.mediaTimed.completes.value | c.a.media.complete | AppMeasurement context data. |
| media.mediaTimed.dropBeforeStart.value |  c.a.media.view, c.a.media.timePlayed, c.a.media.play| AppMeasurement context data. |
| media.mediaTimed.federated.value | c.a.media.federated | AppMeasurement context data `c.a.media.federated` mapping. |
| media.mediaTimed.firstQuartiles.value | c.a.media.progress25 | AppMeasurement context data. |
| media.mediaTimed.mediaSegmentView.value | c.a.media.segmentView | AppMeasurement context data. |
| media.mediaTimed.midpoints.value | c.a.media.progress50 | AppMeasurement context data. |
| media.mediaTimed.pauseTime.value | c.a.media.pauseTime | AppMeasurement context data `c.a.media.pauseTime` mapping. |
| media.mediaTimed.pauses.value | c.a.media.pauseCount | AppMeasurement context data `c.a.media.pauseCount` mapping. |
| media.mediaTimed.primaryAssetReference.@id | c.a.media.asset   | AppMeasurement context data. |
| media.mediaTimed.primaryAssetReference.dc:title | c.a.media.friendlyName | AppMeasurement context data `c.a.media.friendlyName` mapping. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Creator[N].iptc4xmpExt:Name | c.a.media.originator | AppMeasurement context data. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Episode.iptc4xmpExt:Number | c.a.media.episode | AppMeasurement context data `c.a.media.episode` mapping. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Genre | c.a.media.genre | AppMeasurement context data. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue | c.a.media.rating | AppMeasurement context data. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Season.iptc4xmpExt:Number | c.a.media.season | AppMeasurement context data `c.a.media.season` mapping. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Identifier | a.media.name | AppMeasurement context data `a.media.name` mapping. |
| media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Name | c.a.media.show | AppMeasurement context data `c.a.media.show` mapping. |
| media.mediaTimed.primaryAssetReference.showType | c.a.media.type | AppMeasurement context data `c.a.media.type` mapping with conversion VEDIO_SHOW_TYPE. |
| media.mediaTimed.primaryAssetReference.showType | c.a.media.type | AppMeasurement context data `c.a.media.type` mapping with conversion VIDEO_SHOW_TYPE. |
| media.mediaTimed.primaryAssetReference.xmpDM:duration | c.a.media.length | AppMeasurement context data `c.a.media.length` mapping. |
| media.mediaTimed.primaryAssetViewDetails.@id | c.a.media.vsid | AppMeasurement context data. |
| media.mediaTimed.primaryAssetViewDetails.broadcastChannel | c.a.media.channel | AppMeasurement context data `c.a.media.channel` mapping. |
| media.mediaTimed.primaryAssetViewDetails.broadcastContentType | c.a.contentType | AppMeasurement context data `c.a.contentType` mapping. |
| media.mediaTimed.primaryAssetViewDetails.broadcastNetwork | c.a.media.network | AppMeasurement context data `c.a.media.network` mapping. |
| media.mediaTimed.primaryAssetViewDetails.mediaSegmentView.value | c.a.media.segment | AppMeasurement context data `c.a.media.segment` mapping. |
| media.mediaTimed.primaryAssetViewDetails.playerName | c.a.media.playerName | AppMeasurement context data `c.a.media.playerName` mapping. |
| media.mediaTimed.primaryAssetViewDetails.playerSDKVersion.version | c.a.media.sdkVersion | AppMeasurement context data `c.a.media.sdkVersion` mapping. |
| media.mediaTimed.primaryAssetViewDetails.sourceFeed | c.a.media.feed | AppMeasurement context data `c.a.media.feed` mapping. |
| media.mediaTimed.primaryAssetViewDetails.streamFormat | c.a.media.format | AppMeasurement context data `c.a.media.format` mapping. |
| media.mediaTimed.progress10.value | c.a.media.progress10 | AppMeasurement context data. |
| media.mediaTimed.progress95.value | c.a.media.progress95 | AppMeasurement context data. |
| media.mediaTimed.resumes.value | c.a.media.resume | AppMeasurement context data `c.a.media.resume` mapping. |
| media.mediaTimed.starts.value | c.a.media.view | AppMeasurement context data. |
| media.mediaTimed.thirdQuartiles.value | c.a.media.progress75 | AppMeasurement context data. |
| media.mediaTimed.timePlayed.value | c.a.media.timePlayed | AppMeasurement context data `c.a.media.timePlayed` mapping. |
| media.mediaTimed.totalTimePlayed.value | c.a.media.totalTimePlayed | AppMeasurement context data `c.a.media.totalTimePlayed` mapping. |
| placeContext.geo.latitude | lat | AppMeasurement query parameter LATITUDE mapping. |
| placeContext.geo.longitude | lon | AppMeasurement query parameter LONGITUDE mapping. |
| placeContext.geo.postalCode | zip | AppMeasurement query parameter ZIP mapping. |
| placeContext.geo.stateProvince | state | AppMeasurement query parameter STATE mapping. |
| productListItems[N].lineItemId | products | AppMeasurement query parameter Products Category mapping. |
| productlistitems[N].name | products | AppMeasurement query parameter Products Name mapping. |
| productlistitems[N].priceTotal | products | AppMeasurement query parameter Products Price mapping. |
| productlistitems[N].quantity | products | AppMeasurement query parameter Products Quantity mapping. |
| web.webInteraction.URL | pev1 | AppMeasurement query parameter PAGE_EVENT_VAR1 mapping. |
| web.webInteraction.name | pev2 | AppMeasurement query parameter PAGE_EVENT_VAR2 mapping. |
| web.webInteraction.type | pe | `web.webInteraction.type=other` to `pe=lnk_o`; `web.webInteraction.type=download` to `pe=lnk_d`; `web.webInteraction.type=exit` to `pe=lnk_e` |
| web.webPageDetails.URL | g | AppMeasurement query parameter PAGE_URL mapping. |
| web.webPageDetails.errorPage | pageType | AppMeasurement query parameter PAGE_TYPE_FULL mapping with conversion ERROR_PAGE_TYPE. |
| web.webPageDetails.homePage | hp | AppMeasurement query parameter HOMEPAGE mapping with conversion BOOLEAN_TO_YN. |
| web.webPageDetails.name | gn | AppMeasurement query parameter PAGENAME mapping. |
| web.webPageDetails.server | sv | AppMeasurement query parameter USER_SERVER mapping. |
| web.webPageDetails.siteSection | ch | AppMeasurement query parameter CHANNEL mapping. |
| web.webReferrer.URL | r | AppMeasurement query parameter REFERRER mapping. |

{style="table-layout:auto"}