---
title: ActivityMap.regionIDAttribute
description: Change the attribute that Activity Map looks for to determine the region.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: 'https://experienceleague.adobe.com/DJj1qmoYB0iMxDszdGKYTeczkjv0OvxXAYlg2irpKb0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# ActivityMap.regionIDAttribute

The `ActivityMap.regionIDAttribute` variable lets you change the attribute that Activity Map looks for when determining the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension. If your site is structured in a way that makes the `id` attribute less useful for Activity Map region, you can set this variable to look at a different attribute.

## Region ID attribute in the Web SDK extension

When **[!UICONTROL Enable click data collection]** is enabled, use the **[!UICONTROL Filter click properties]** callback code block. Within this code block, you can check the value of `content.clickedElement`, and either change the value or abandon the collection of link tracking data.

## Region ID attribute in the Web SDK JavaScript library

When [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) is enabled, use the `filterClickDetails` callback in the `clickCollection` object. Inside this callback, you can check the value of `clickedElement`, and customize the logic of the region collected.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Region ID attribute using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.ActivityMap.regionIDAttribute using AppMeasurement

The `s.ActivityMap.regionIDAttribute` variable is a string that represents the attribute to determine the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension. This variable is set to `id` by default. If you change this variable, Activity Map no longer looks for the `id` attribute, but still looks for other criteria to determine region (such as semantic elements).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
