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
| `xdm.application.isClose` | Helps define the mobile lifecycle metric [Crashes](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Helps determine when to increase the mobile lifecycle metric [First Launches](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determines if a close event is a crash or not. Valid values include `close` (A lifecycle session ends and a pause event was received for the previous session) and `unknown` (A lifecycle session ends without a pause event). Helps set the mobile lifecycle metric [Crashes](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/) metric. |
| `xdm.application.isInstall` | The mobile lifecycle metric [Installs](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | The mobile lifecycle metric [Launches](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Helps set the mobile lifecycle dimension [App ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | The mobile lifecycle metric [Upgrades](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Helps set the mobile lifecycle dimension [App ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | The mobile lifecycle metric [Previous Session Length](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Checkouts](/help/components/metrics/checkouts.md) metric. |
| `xdm.commerce.checkouts.value` | Increments the [Checkouts](/help/components/metrics/checkouts.md) metric by the desired amount. |
| `xdm.commerce.order.currencyCode` | Sets the [currencyCode](../vars/config-vars/currencycode.md) configuration variable. |
| `xdm.commerce.order.purchaseID` | Sets the [purchaseID](../vars/page-vars/purchaseid.md) page variable. |
| `xdm.commerce.order.payments[0].transactionID` | Sets the [transactionID](../vars/page-vars/transactionid.md) page variable. |
| `xdm.commerce.productListAdds.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Additions](/help/components/metrics/cart-additions.md) metric. |
| `xdm.commerce.productListAdds.value` | Increments the [Cart Additions](/help/components/metrics/cart-additions.md) metric. |
| `xdm.commerce.productListOpens.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Carts](/help/components/metrics/carts.md) metric. |
| `xdm.commerce.productListOpens.value` | Increments the [Carts](/help/components/metrics/carts.md) metric. |
| `xdm.commerce.productListRemovals.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Removals](/help/components/metrics/cart-removals.md) metric. |
| `xdm.commerce.productListRemovals.value` | Increments the [Cart Removals](/help/components/metrics/cart-removals.md) metric. |
| `xdm.commerce.productListViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Cart Views](/help/components/metrics/cart-views.md) metric. |
| `xdm.commerce.productListViews.value` | Increments the [Cart Views](/help/components/metrics/cart-views.md) metric. |
| `xdm.commerce.productViews.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the [Product Views](/help/components/metrics/product-views.md) metric. |
| `xdm.commerce.productViews.value` | Increments the [Product Views](/help/components/metrics/product-views.md) metric. |
| `xdm.commerce.purchases.value` | Increments the [Orders](/help/components/metrics/orders.md) metric. |
| `xdm.device.model` | The mobile lifecycle dimension [Device Name](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Helps set the [Color Depth](/help/components/dimensions/color-depth.md) dimension. |
| `xdm.device.screenHeight` | Helps set the [Monitor Resolution](/help/components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.screenWidth` | Helps set the [Monitor Resolution](/help/components/dimensions/monitor-resolution.md) dimension. |
| `xdm.device.type` | The mobile device type. |
| `xdm.environment.browserDetails.acceptLanguage` | Helps set the [Language](/help/components/dimensions/language.md) dimension. |
| `xdm.environment.browserDetails.cookiesEnabled` | Sets the [Cookie Support](/help/components/dimensions/cookie-support.md) dimension. Valid values include `Y` (the browser accepts cookies) and `N` (the browser rejects cookies). |
| `xdm.environment.browserDetails.javaEnabled` | Sets the [Java enabled](/help/components/dimensions/java-enabled.md) dimension. Valid values include `Y` (Java is enabled) and `N` (Java is disabled). |
| `xdm.environment.browserDetails.userAgent` | Used as a fallback [unique visitor](/help/components/metrics/unique-visitors.md) identification method. Typically populated using the `User-Agent` HTTP request header. You can map this field to an eVar if you would like to use it in reports. |
| `xdm.environment.browserDetails.viewportHeight` | Sets the [Browser Height](/help/components/dimensions/browser-height.md) dimension. |
| `xdm.environment.browserDetails.viewportWidth` | Sets the [Browser Width](/help/components/dimensions/browser-width.md) dimension. |
| `xdm.environment.carrier` | The mobile lifecycle dimension [Carrier Name](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Helps set the [Connection type](/help/components/dimensions/connection-type.md) dimension. |
| `xdm.environment.ipV4` | Used as a fallback [unique visitor](/help/components/metrics/unique-visitors.md) identification method. Typically populated using the `X-Forwarded-For` HTTP header. |
| `xdm.environment._dc.language` | The mobile dimension Locale. Used only if xdm.environment.language is not set. |
| `xdm.environment.language` | The mobile dimension Locale. |
| `xdm.environment.operatingSystem` | The mobile lifecycle dimension [Operating System](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Helps set the mobile lifecycle dimension [Operating System Version](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Sets the respective [eVar](/help/components/dimensions/evar.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Sets the respective [Hierarchy](/help/components/dimensions/hierarchy.md) dimension. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` |  List prop delimiter override. Using this field is not recommended, as the delimiter is automatically retrieved from [Traffic variable admin](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) under report suite settings. Using this field can create a mismatch between the delimiter used and the delimiter that Analytics expects. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | A string array containing the respective [List Prop](../vars/page-vars/prop.md#list-props) values. |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatenates all `value` strings in each respective `list[]` array to its respective [List variable](../vars/page-vars/list.md). The delimiter is automatically chosen based on the value set in [Report suite settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Sets the respective [Prop](/help/components/dimensions/prop.md) dimension. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Applies [event serialization](../vars/page-vars/events/event-serialization.md) to the respective [Custom events](/help/components/metrics/custom-events.md) metric. Each event ID resides in its 100-group parent. For example, to apply serialization to `event678`, use `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Increments the respective [Custom events](/help/components/metrics/custom-events.md) metric by the desired amount. Each event resides in its 100-group parent. For example, the field for `event567` is `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | The [Adobe Experience Cloud Identity Service ID](https://experienceleague.adobe.com/en/docs/id-service/using/home). |
| `xdm.marketing.trackingCode` | Sets the [Tracking Code](/help/components/dimensions/tracking-code.md) dimension. |
| `xdm.media.mediaTimed.completes.value` | The streaming media metric [Content Complete](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | The streaming media metric [Federated Data](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | The streaming media metric [Twenty-five % Progress Marker](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#twenty-five--progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | The streaming media metric [Content Segment Views](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | The streaming media metric [Fifty % Progress Marker](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | The streaming media metric [Total Pause Duration](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | The streaming media metric [Pause Events](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#pause-events). |
| `xdm.mediaCollection.sessionDetails.assetID` | The streaming media dimension [Asset ID](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#asset-id). |
| `xdm.mediaCollection.sessionDetails.friendlyName` | The streaming media dimension [Video Name](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-name). |
| `xdm.mediaCollection.sessionDetails.originator` | The streaming media dimension [Originator](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#originator). |
| `xdm.mediaCollection.sessionDetails.episode` | The streaming media dimension [Episode](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#episode). |
| `xdm.mediaCollection.sessionDetails.genre` | The streaming media dimension [Genre](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#genre). |
| `xdm.mediaCollection.sessionDetails.rating` | The streaming media dimension [Content Rating](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-rating). |
| `xdm.mediaCollection.sessionDetails.season` | The streaming media dimension [Season](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#season). |
| `xdm.mediaCollection.sessionDetails.name` | The streaming media dimension [Content ID](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-id). |
| `xdm.mediaCollection.sessionDetails.show` | The streaming media dimension [Show](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show). |
| `xdm.mediaCollection.sessionDetails.showType` | The streaming media dimension [Show Type](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show-type). |
| `xdm.mediaCollection.sessionDetails.length` | The streaming media dimension [Video Length](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.@id` | The streaming media dimension [Media Session ID](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-session-id). |
| `xdm.mediaCollection.sessionDetails.channel` | The streaming media dimension [Content Channel](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-channel). |
| `xdm.mediaCollection.sessionDetails.contentType` | The streaming media dimension [Content Type](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-type). |
| `xdm.mediaCollection.sessionDetails.network` | The streaming media dimension [Network](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | The streaming media dimension [Content Segment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment). |
| `xdm.mediaCollection.sessionDetails.playerName` | The streaming media dimension [Content Player Name](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-player-name). |
| `xdm.mediaCollection.sessionDetails.appVersion` | The streaming media dimension [SDK Version](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#sdk-version). |
| `xdm.mediaCollection.sessionDetails.feed` | The streaming media dimension [Media Feed Type](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-feed-type). |
| `xdm.mediaCollection.sessionDetails.streamFormat` | The streaming media dimension [Stream Format](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | The streaming media metric [Ten % Progress Marker](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ten--progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | The streaming media metric [Ninety-five % Progress Marker](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ninety-five--progress-marker). |
| `xdm.mediaCollection.sessionDetails.hasResume` | The streaming media metric [Content Resumes](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | The streaming media metric [Media Starts](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | The streaming media metric [Seventy-five % Progress Marker](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#seventy-five--progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | The streaming media metric [Content Time Spent](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | The streaming media metric [Media Time Spent](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | The visitor's latitude location. Helps set [Mobile lifecycle location](/help/components/dimensions/lifecycle-dimensions.md) dimensions. |
| `xdm.placeContext.geo._schema.longitude` | The visitor's longitude location. Helps set [Mobile lifecycle location](/help/components/dimensions/lifecycle-dimensions.md) dimensions. |
| `xdm.placeContext.geo.postalCode` | The [Zip Code](/help/components/dimensions/zip-code.md) dimension. |
| `xdm.placeContext.geo.stateProvince` | The [US States](/help/components/dimensions/us-states.md) dimension. |
| `xdm.placeContext.localTime` | Appears as `t_time_info` in [Data feeds](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applies [product syntax](../vars/page-vars/products.md) merchandising to eVars. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applies [product syntax](../vars/page-vars/products.md) merchandising to events. |
| `xdm.productListItems[].productCategories[].categoryID` | The [Category](/help/components/dimensions/category.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].name` | The [Product](/help/components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `xdm.productListItems[].SKU` and `xdm.productListItems[].name` both contain data, the value in `xdm.productListItems[].SKU` is used. |
| `xdm.productListItems[].priceTotal` | Helps determine the [Revenue](/help/components/metrics/revenue.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].quantity` | Helps determine the [Units](/help/components/metrics/units.md) metric. See also the [products](../vars/page-vars/products.md) page variable. |
| `xdm.productListItems[].SKU` | The [Product](/help/components/dimensions/product.md) dimension. See also the [products](../vars/page-vars/products.md) page variable. If `xdm.productListItems[].SKU` and `xdm.productListItems[].name` both contain data, the value in `xdm.productListItems[].SKU` is used. |
| `xdm.web.webInteraction.URL` | The [linkURL](../vars/config-vars/linkurl.md) implementation variable. |
| `xdm.web.webInteraction.name` | The [Custom link](/help/components/dimensions/custom-link.md), [Download link](/help/components/dimensions/download-link.md), or [Exit link](/help/components/dimensions/exit-link.md) dimension, depending on the value in `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determines the type of link clicked. Valid values include `other` (Custom links), `download` (Download links), and `exit` (Exit links). |
| `xdm.web.webPageDetails.URL` | The [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `xdm.web.webPageDetails.isErrorPage` | Flag that helps determine the 'Pages Not Found' [dimension](/help/components/dimensions/pages-not-found.md) and [metric](/help/components/metrics/pages-not-found.md). |
| `xdm.web.webPageDetails.name` | The [Page](/help/components/dimensions/page.md) dimension. |
| `xdm.web.webPageDetails.server` | The [Server](/help/components/dimensions/server.md) dimension. |
| `xdm.web.webPageDetails.siteSection` | The [Site Section](/help/components/dimensions/site-section.md) dimension. |
| `xdm.web.webReferrer.URL` | The [Referrer](/help/components/dimensions/referrer.md) dimension. |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mapping other XDM fields to Analytics variables

If there are any dimensions or metrics that you want to add to Adobe Analytics, you can do so through [Context data variables](../vars/page-vars/contextdata.md). 

### Implicit mapping

Any XDM field elements that are not automatically mapped are sent to Adobe Analytics as context data with the prefix `a.x.`. You can then map this context data variable to the desired Analytics variable using [processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md). For example, if you send the following event:

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

The Web SDK sends that data to Adobe Analytics as the context data variable `a.x._atag.search.term`. You can then use a processing rule to assign that context data variable value to the desired Analytics variable, such as an `eVar`:

![Search term processing rule](assets/examplerule.png)

## Explicit mapping

You can also explicitly map XDM field elements as context data. Any XDM field element that is explicitly mapped, using the `contextData` element, is sent to Adobe Analytics as context data without a prefix. You can then map this context data variable to the desired Analytics variable using [processing rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md). For example, if you send the following event:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

The Web SDK sends that data to Adobe Analytics as the context data variable `somevalue` with value `1`.  You can then use a processing rule to assign that context data variable value to the desired Analytics variable, such as an `eVar`:

 ![Search term processing rule](assets/examplerule-explicit.png)
