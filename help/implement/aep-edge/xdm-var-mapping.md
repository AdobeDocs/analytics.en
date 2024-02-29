---
title: XDM object variable mapping to Adobe Analytics
description: View which XDM fields that Edge automatically maps to Analytics variables.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
---
# XDM object variable mapping to Adobe Analytics

The following table shows the XDM variables that the Adobe Experience Platform Edge Network automatically maps into Adobe Analytics. If you use these XDM field paths, no additional configuration is necessary to send data to Adobe Analytics. These fields are included in the **[!UICONTROL Adobe Analytics ExperienceEvent Template]** field group. Use of these fields are recommended if you intend to send data to both Adobe Analytics and Adobe Experience Platform.

If your organization plans to move to Customer Journey Analytics, Adobe recommends instead using the `data` object to send data directly to Adobe Analytics without conforming to a schema. This strategy allows your organization to use your own schema, instead of using the [!UICONTROL Adobe Analytics ExperienceEvent Template] (which is less applicable to Customer Journey Analytics). See [Data object variable mapping to Adobe Analytics](data-var-mapping.md) for a similar mapping table.

## Value priorities

Most XDM object fields in this table coincide with a [data object field](data-var-mapping.md). If you set both a given XDM object field and its respective data object field, the data object field takes priority. If you use both the XDM object field and the data object field, Adobe recommends setting custom events using the data object field. If the field `data.__adobe.analytics.events` is present, it overwrites all XDM object fields related commerce and custom events.

## XDM object field mapping

Previous updates to this table can be found on this page's [commit history on GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md).

| XDM field path | Analytics variable and description |
| --- | --- |
| `xdm.application.isClose` | Helps define the mobile lifecycle metric [Crashes](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Helps determine when to increase the mobile lifecycle metric [First Launches](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | Helps determine when to increase the mobile lifecycle metric [First Launches](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determines if a close event is a crash or not. Valid values include `close` (A lifecycle session ends and a pause event was received for the previous session) and `unknown` (A lifecycle session ends without a pause event). Helps set the mobile lifecycle metric [Crashes](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) metric. |
| `xdm.application.isInstall` | The mobile lifecycle metric [Installs](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | The mobile lifecycle metric [Launches](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Helps set the mobile lifecycle dimension [App ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | The mobile lifecycle metric [Upgrades](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Helps set the mobile lifecycle dimension [App ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | The mobile lifecycle metric [Previous Session Length](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Checkouts](../../components/metrics/checkouts.md) metric. |
| `xdm.commerce.checkouts.value` | Increments the [Checkouts](../../components/metrics/checkouts.md) metric by the desired amount. |
| `xdm.commerce.order.currencyCode` | Sets the [currencyCode](../vars/config-vars/currencycode.md) configuration variable. |
| `xdm.commerce.order.purchaseID` | Sets the [purchaseID](../vars/page-vars/purchaseid.md) page variable. |
| `xdm.commerce.order.payments[0].transactionID` | Sets the [transactionID](../vars/page-vars/transactionid.md) page variable. |
| `xdm.commerce.productListAdds.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Additions](../../components/metrics/cart-additions.md) metric. |
| `xdm.commerce.productListAdds.value` | Increments the [Cart Additions](../../components/metrics/cart-additions.md) metric. |
| `xdm.commerce.productListOpens.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Carts](../../components/metrics/carts.md) metric. |
| `xdm.commerce.productListOpens.value` | Increments the [Carts](../../components/metrics/carts.md) metric. |
| `xdm.commerce.productListRemovals.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Removals](../../components/metrics/cart-removals.md) metric. |
| `xdm.commerce.productListRemovals.value` | Increments the [Cart Removals](../../components/metrics/cart-removals.md) metric. |
| `xdm.commerce.productListViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Views](../../components/metrics/cart-views.md) metric. |
| `xdm.commerce.productListViews.value` | Increments the [Cart Views](../../components/metrics/cart-views.md) metric. |
| `xdm.commerce.productViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Product Views](../../components/metrics/product-views.md) metric. |
| `xdm.commerce.productViews.value` | Increments the [Product Views](../../components/metrics/product-views.md) metric. |
| `xdm.commerce.purchases.value` | Increments the [Orders](../../components/metrics/orders.md) metric. |
| `xdm.device.model` | The mobile lifecycle dimension [Device Name](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Helps set the [Color Depth](../../components/dimensions/color-depth.md) dimension. |
| `xdm.device.screenHeight` | Helps set the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.screenWidth` | Helps set the [Monitor Resolution](../../components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.type` | The mobile device type. |
| `xdm.environment.browserDetails.acceptLanguage` | Helps set the [Language](../../components/dimensions/language.md) dimension. |
| `xdm.environment.browserDetails.cookiesEnabled` | Sets the [Cookie Support](../../components/dimensions/cookie-support.md) dimension. Valid values include `Y` (the browser accepts cookies) and `N` (the browser rejects cookies). |
| `xdm.environment.browserDetails.javaEnabled` | Sets the [Java enabled](../../components/dimensions/java-enabled.md) dimension. Valid values include `Y` (Java is enabled) and `N` (Java is disabled). |
| `xdm.environment.browserDetails.userAgent` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `User-Agent` HTTP request header. You can map this field to an eVar if you would like to use it in reports. |
| `xdm.environment.browserDetails.viewportHeight` | Sets the [Browser Height](../../components/dimensions/browser-height.md) dimension. |
| `xdm.environment.browserDetails.viewportWidth` | Sets the [Browser Width](../../components/dimensions/browser-width.md) dimension. |
| `xdm.environment.carrier` | The mobile lifecycle dimension [Carrier Name](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Helps set the [Connection type](../../components/dimensions/connection-type.md) dimension. |
| `xdm.environment.ipV4` | Used as a fallback [unique visitor](../../components/metrics/unique-visitors.md) identification method. Typically populated using the `X-Forwarded-For` HTTP header. |
| `xdm.environment.language` | The mobile dimension Locale. |
| `xdm.environment.operatingSystem` | The mobile lifecycle dimension [Operating System](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Helps set the mobile lifecycle dimension [Operating System Version](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Sets the respective [eVar](../../components/dimensions/evar.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Sets the respective [Hierarchy](/help/components/dimensions/hierarchy.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` |  List prop delimiter override. Using this field is not recommended, as the delimiter is automatically retrieved from [Traffic variable admin](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) under report suite settings. Using this field can create a mismatch between the delimiter used and the delimiter that Analytics expects. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | A string array containing the respective [List Prop](../vars/page-vars/prop.md#list-props) values. |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatenates all `value` strings in each respective `list[]` array to its respective [List variable](../vars/page-vars/list.md). Delimiter is automatically chosen based on the value set in [Report suite settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Sets the respective [Prop](../../components/dimensions/prop.md) dimension. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the respective [Custom events](../../components/metrics/custom-events.md) metric. Each event ID resides in its 100-group parent. For example, to apply serialization to `event678`, use `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Increments the respective [Custom events](../../components/metrics/custom-events.md) metric by the desired amount. Each event resides in its 100-group parent. For example, the field for `event567` is `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | The [Adobe Experience Cloud Identity Service ID](https://experienceleague.adobe.com/docs/id-service/using/home.html). |
| `xdm.marketing.trackingCode` | Sets the [Tracking Code](../../components/dimensions/tracking-code.md) dimension. |
| `xdm.media.mediaTimed.completes.value` | The Media Analytics metric [Content Complete](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | The Media Analytics metric [Federated Data](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | The Media Analytics metric [Twenty-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | The Media Analytics metric [Content Segment Views](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | The Media Analytics metric [Fifty % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | The Media Analytics metric [Total Pause Duration](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | The Media Analytics metric [Pause Events](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`@id` | The Media Analytics dimension [Asset ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | The Media Analytics dimension [Video Name](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | The Media Analytics dimension [Originator](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | The Media Analytics dimension [Episode](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | The Media Analytics dimension [Genre](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | The Media Analytics dimension [Content Rating](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | The Media Analytics dimension [Season](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | The Media Analytics dimension [Content ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | The Media Analytics dimension [Show](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`showType` | The Media Analytics dimension [Show Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | The Media Analytics dimension [Video Length](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | The Media Analytics dimension [Media Session ID](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | The Media Analytics dimension [Content Channel](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | The Media Analytics dimension [Content Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | The Media Analytics dimension [Network](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | The Media Analytics dimension [Content Segment](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | The Media Analytics dimension [Content Player Name](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | The Media Analytics dimension [SDK Version](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | The Media Analytics dimension [Media Feed Type](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | The Media Analytics dimension [Stream Format](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | The Media Analytics metric [Ten % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | The Media Analytics metric [Ninety-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `xdm.media.mediaTimed.resumes.value` | The Media Analytics metric [Content Resumes](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | The Media Analytics metric [Media Starts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | The Media Analytics metric [Seventy-five % Progress Marker](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | The Media Analytics metric [Content Time Spent](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | The Media Analytics metric [Media Time Spent](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | The Mobile dimension Latitude. |
| `xdm.placeContext.geo._schema.longitude` | The Mobile dimension Longitude. |
| `xdm.placeContext.geo.postalCode` | The [Zip Code](../../components/dimensions/zip-code.md) dimension. |
| `xdm.placeContext.geo.stateProvince` | The [US States](../../components/dimensions/us-states.md) dimension. |
| `xdm.placeContext.localTime` | Appears as `t_time_info` in [Data feeds](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applies [product syntax](../vars/page-vars/products.md) merchandising to eVars. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applies [product syntax](../vars/page-vars/products.md) merchandising to events. |
| `xdm.productListItems[].productCategories[].categoryID` | The [Category](../../components/dimensions/category.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].name` | The [Product](../../components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `xdm.productListItems[].SKU` and `xdm.productListItems[].name` both contain data, the value in `xdm.productListItems[].SKU` is used. |
| `xdm.productListItems[].priceTotal` | Helps determine the [Revenue](../../components/metrics/revenue.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].quantity` | Helps determine the [Units](../../components/metrics/units.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].SKU` | The [Product](../../components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `xdm.productListItems[].SKU` and `xdm.productListItems[].name` both contain data, the value in `xdm.productListItems[].SKU` is used. |
| `xdm.web.webInteraction.URL` | The [linkURL](../vars/config-vars/linkurl.md) implementation variable. |
| `xdm.web.webInteraction.name` | The [Custom link](../../components/dimensions/custom-link.md), [Download link](../../components/dimensions/download-link.md), or [Exit link](../../components/dimensions/exit-link.md) dimension, depending on the value in `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determines the type of link clicked. Valid values include `other` (Custom links), `download` (Download links), and `exit` (Exit links). |
| `xdm.web.webPageDetails.URL` | The [Page URL](../../components/dimensions/page-url.md) dimension. |
| `xdm.web.webPageDetails.isErrorPage` | Flag that helps determine the 'Pages Not Found' [dimension](../../components/dimensions/pages-not-found.md) and [metric](../../components/metrics/pages-not-found.md). |
| `xdm.web.webPageDetails.name` | The [Page](../../components/dimensions/page.md) dimension. |
| `xdm.web.webPageDetails.server` | The [Server](../../components/dimensions/server.md) dimension. |
| `xdm.web.webPageDetails.siteSection` | The [Site Section](../../components/dimensions/site-section.md) dimension. |
| `xdm.web.webReferrer.URL` | The [Referrer](../../components/dimensions/referrer.md) dimension. |

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
