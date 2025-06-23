---
title: ActivityMap.linkExclusions
description: Filter Activity Map data by link name.
role: Admin, Developer
feature: AppMeasurement implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
---
# ActivityMap.linkExclusions

The `ActivityMap.linkExclusions` variable lets you selectively filter or exclude Activity Map data based on the text in the [Activity Map Link](/help/components/dimensions/activity-map-link.md) dimension.

## Link exclusions in the Web SDK extension

When **[!UICONTROL Enable click data collection]** is enabled, use the **[!UICONTROL Filter click properties]** callback code block. Within this code block, you can check the value of `content.linkName`, and either change the value or abandon the collection of link tracking data.

## Link exclusions in the Web SDK JavaScript library

When [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) is enabled, use the `filterClickDetails` callback in the `clickCollection` object. Inside this callback, you can check the value of `linkName`, and either change the value or abandon the collection of link tracking data.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## Link exclusions using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## s.ActivityMap.linkExclusions using AppMeasurement

The `s.ActivityMap.linkExclusions` variable is a string containing comma-delimited values of phrases to exclude from Activity Map tracking. If any of the phrases match the value collected in the [Activity Map Link](/help/components/dimensions/activity-map-link.md) dimension, all Activity Map data is removed from the hit. Note that this variable looks at `linkName`, not `linkUrl`.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
