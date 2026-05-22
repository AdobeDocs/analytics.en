---
title: ActivityMap.linkExclusions
description: Filter Activity Map data by link name.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
TQID: 'https://experienceleague.adobe.com/m4ovqFSZBZ88KFm8lnKRI7z5wbbTNZygEj8koL6HC6E'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
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
