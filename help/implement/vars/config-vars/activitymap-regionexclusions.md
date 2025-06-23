---
title: ActivityMap.regionExclusions
description: Filter Activity Map data by region.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
---
# ActivityMap.regionExclusions

The `ActivityMap.regionExclusions` variable lets you selectively filter or exclude Activity Map data based on the dimension items collected in the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension.

## Region exclusions in the Web SDK extension

When **[!UICONTROL Enable click data collection]** is enabled, use the **[!UICONTROL Filter click properties]** callback code block. Within this code block, you can check the value of `content.linkRegion`, and either change the value or abandon the collection of link tracking data.

## Region exclusions in the Web SDK JavaScript library

When [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) is enabled, use the `filterClickDetails` callback in the `clickCollection` object. Inside this callback, you can check the value of `linkRegion`, and either change the value or abandon the collection of link tracking data.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Region exclusions using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.ActivityMap.regionExclusions using AppMeasurement

The `s.ActivityMap.regionExclusions` variable is a string containing comma-delimited phrases to exclude from Activity Map tracking. If any of the phrases match the value collected in the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension, all Activity Map data is removed from the hit.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
