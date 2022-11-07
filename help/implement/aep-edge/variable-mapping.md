---
title: Analytics variable mapping in Adobe Experience Edge
description: View which XDM fields that Edge automatically maps to Analytics variables.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
---
# Analytics variable mapping in Adobe Experience Edge

The following table shows the variables that the Adobe Experience Platform Edge Network automatically maps into Adobe Analytics. If you use these XDM Field Paths, no additional configuration is necessary to send data to Adobe Analytics.

| XDM Field Path  | Analytics dimension and description |
| --- | --- |
| `application.isClose` | Helps define the mobile metric [Crashes](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isInstall` | Helps determine when to increase the mobile metric [First Launches](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Helps determine when to increase the mobile metric [First Launches](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determines if a close event is a crash or not. Valid values include `close` (A lifecycle session ends and a pause event was received for the previous session) and `unknown` (A lifecycle session ends without a pause event). Helps set the [Crashes](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics) metric. |
| `application.isInstall` | The mobile metric [Installs](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | The mobile metric [Launches](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Helps set the mobile dimension [App ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isUpgrade` | The mobile metric [Upgrades](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Helps set the mobile dimension [App ID](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | The mobile metric [Previous Session Length](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Checkouts](../../components/metrics/checkouts.md) metric. |
| `commerce.checkouts.value` | Increments the [Checkouts](../../components/metrics/checkouts.md) metric by the desired amount. |
| `commerce.order.currencyCode` | Sets the [currencyCode](../vars/config-vars/currencycode.md) configuration variable. |
| `commerce.order.purchaseID` | Sets the [purchaseID](../vars/page-vars/purchaseid.md) page variable. |
| `commerce.order.transactionID` | Sets the [transactionID](../vars/page-vars/transactionid.md) page variable. |
| `commerce.productListAdds.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Additions](../../components/metrics/cart-additions.md) metric. |
| `commerce.productListAdds.value` | Increments the [Cart Additions](../../components/metrics/cart-additions.md) metric. |
| `commerce.productListOpens.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Carts](../../components/metrics/carts.md) metric. |
| `commerce.productListOpens.value` | Increments the [Carts](../../components/metrics/carts.md) metric. |
| `commerce.productListRemovals.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Removals](../../components/metrics/cart-removals.md) metric. |
| `commerce.productListRemovals.value` | Increments the [Cart Removals](../../components/metrics/cart-removals.md) metric. |
| `commerce.productListViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Views](../../components/metrics/cart-views.md) metric. |
| `commerce.productListViews.value` | Increments the [Cart Views](../../components/metrics/cart-views.md) metric. |
| `commerce.productViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Product Views](../../components/metrics/product-views.md) metric. |
| `commerce.productViews.value` | Increments the [Product Views](../../components/metrics/product-views.md) metric. |
| `commerce.purchases.value` | Increments the [Orders](../../components/metrics/orders.md) metric. |
| `device.model` | The mobile dimension [Device Name](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.colorDepth` | Helps set the [Color Depth](../../components/dimensions/color-depth.md) dimension. |
| `device.screenHeight` | Helps set the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. |
| `device.screenWidth` | Helps set the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. |
| `device.type` | The mobile device type. |
| `environment.browserDetails.acceptLanguage` | Helps set the [Language](../../components/dimensions/language.md) dimension. |
| `environment.browserDetails.cookiesEnabled` | Sets the [Cookie Support](../../components/dimensions/cookie-support.md) dimension. Valid values include `Y` (the browser accepts cookies) and `N` (the browser rejects cookies). |
| `environment.browserDetails.javaEnabled` | Sets the [Java enabled](../../components/dimensions/java-enabled.md) dimension. Valid values include `Y` (Java is enabled) and `N` (Java is disabled). |
| `environment.browserDetails.userAgent` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `User-Agent` HTTP request header. You can map this field to an eVar if you would like to use it in reports. |
| `environment.browserDetails.viewportHeight` | Sets the [Browser Height](../../components/dimensions/browser-height.md) dimension. |
| `environment.browserDetails.viewportWidth` | Sets the [Browser Width](../../components/dimensions/browser-width.md) dimension. |
| `environment.carrier` | The mobile dimension [Carrier Name](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Helps set the [Connection type](../../components/dimensions/connection-type.md) dimension. |
| `environment.ipV4` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `X-Forwarded-For` HTTP header. |
| `environment.language` | The mobile dimension Locale. |
| `environment.operatingSystem` | The mobile dimension [Operating System](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | Helps set the [Operating System Version](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions) dimension. |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Sets the respective [eVar](../../components/dimensions/evar.md) dimension. |
| `_experience.analytics.customDimensions.`<br/>`hierarchies.hier1` -<br/>`_experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Sets the respective [Hierarchy](/help/components/dimensions/hierarchy.md) dimension. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` |  List prop delimiter override. Using this field is not recommended, as the delimiter is automatically retrieved from [Traffic variable admin](/help/admin/admin/c-traffic-variables/traffic-var.md) under report suite settings. Using this field can create a mismatch between the delimiter used and the delimiter that Analytics expects. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | A string array containing the respective [List Prop](../vars/page-vars/prop.md#list-props) values. |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatenates all `value` strings in each respective `list[]` array to its respective [List variable](../vars/page-vars/list.md). Delimiter is automatically chosen based on the value set in [Report suite settings](/help/admin/admin/conversion-var-admin/list-var-admin.md). |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Sets the respective [Prop](../../components/dimensions/prop.md) dimension. |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the respective [Custom events](../../components/metrics/custom-events.md) metric. |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Increments the respective [Custom events](../../components/metrics/custom-events.md) metric by the desired amount. |
| `identityMap.ECID[0].id` | The [Adobe Experience Cloud Identity Service ID](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| `marketing.trackingCode` | Sets the [Tracking Code](../../components/dimensions/tracking-code.md) dimension. |
| `media.mediaTimed.completes.value` | The Media Analytics metric [Content Complete](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | The Media Analytics metric [Federated Data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | The Media Analytics metric [Twenty-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | The Media Analytics metric [Content Segment Views](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | The Media Analytics metric [Fifty % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | The Media Analytics metric [Total Pause Duration](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | The Media Analytics metric [Pause Events](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | The Media Analytics dimension [Asset ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | The Media Analytics dimension [Video Name](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | The Media Analytics dimension [Originator](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | The Media Analytics dimension [Episode](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | The Media Analytics dimension [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | The Media Analytics dimension [Content Rating](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | The Media Analytics dimension [Season](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | The Media Analytics dimension [Content ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | The Media Analytics dimension [Show](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | The Media Analytics dimension [Show Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | The Media Analytics dimension [Video Length](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | The Media Analytics dimension [Media Session ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | The Media Analytics dimension [Content Channel](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | The Media Analytics dimension [Content Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | The Media Analytics dimension [Network](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | The Media Analytics dimension [Content Segment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | The Media Analytics dimension [Content Player Name](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | The Media Analytics dimension [SDK Version](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | The Media Analytics dimension [Media Feed Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | The Media Analytics dimension [Stream Format](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | The Media Analytics metric [Ten % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | The Media Analytics metric [Ninety-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | The Media Analytics metric [Content Resumes](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | The Media Analytics metric [Media Starts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | The Media Analytics metric [Seventy-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | The Media Analytics metric [Content Time Spent](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | The Media Analytics metric [Media Time Spent](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | The Mobile dimension Latitude. |
| `placeContext.geo.longitude` | The Mobile dimension Longitude. |
| `placeContext.geo.postalCode` | The [Zip Code](../../components/dimensions/zip-code.md) dimension. |
| `placeContext.geo.stateProvince` | The [US States](../../components/dimensions/us-states.md) dimension. |
| `placeContext.localTime` | Helps populate [Time Zones](/help/analyze/reports-analytics/reports.md) in Report & Analytics. Appears as `t_time_info` in [Data feeds](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applies [product syntax](../vars/page-vars/products.md) merchandising to eVars. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applies [product syntax](../vars/page-vars/products.md) merchandising to events. |
| `productListItems[].lineItemId` | The [Category](../../components/dimensions/category.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. |
| `productListItems[].name` | The [Product](../../components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `productListItems[].SKU` and `productListItems[].name` both contain data, the value in `productListItems[].SKU` is used. |
| `productListItems[].priceTotal` | Helps determine the [Revenue](../../components/metrics/revenue.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `productListItems[].quantity` | Helps determine the [Units](../../components/metrics/units.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `productListItems[].SKU` | The [Product](../../components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `productListItems[].SKU` and `productListItems[].name` both contain data, the value in `productListItems[].SKU` is used. |
| `web.webInteraction.URL` | The [linkURL](../vars/config-vars/linkurl.md) implementation variable. |
| `web.webInteraction.name` | The [Custom link](../../components/dimensions/custom-link.md), [Download link](../../components/dimensions/download-link.md), or [Exit link](../../components/dimensions/exit-link.md) dimension, depending on the value in `web.webInteraction.type` |
| `web.webInteraction.type` | Determines the type of link clicked. Valid values include `other` (Custom links), `download` (Download links), and `exit` (Exit links). |
| `web.webPageDetails.URL` | The [Page URL](../../components/dimensions/page-url.md) dimension. |
| `web.webPageDetails.errorPage` | Flag that helps determine the 'Pages Not Found' [dimension](../../components/dimensions/pages-not-found.md) and [metric](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | The [Page](../../components/dimensions/page.md) dimension. |
| `web.webPageDetails.server` | The [Server](../../components/dimensions/server.md) dimension. |
| `web.webPageDetails.siteSection` | The [Site Section](../../components/dimensions/site-section.md) dimension. |
| `web.webReferrer.URL` | The [Referrer](../../components/dimensions/referrer.md) dimension. |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mapping other XDM fields to Analytics variables

If there are any dimensions or metrics that you want to add to Adobe Analytics, you can do so through [Context Data variables](../vars/page-vars/contextdata.md). Any XDM field elements that are not automatically mapped are sent to Adobe Analytics as Context Data with the prefix a.x. You can then map this context data variable to the desired Analytics variable using [Processing rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html). For example, if you send the following event:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

The Web SDK sends that data to Adobe Analytics as the context data variable `a.x._atag.search.term`. You can then use a processing rule to assign that context data variable value to the desired Analytics variable, such as an eVar:

![Search term processing rule](assets/examplerule.png)
