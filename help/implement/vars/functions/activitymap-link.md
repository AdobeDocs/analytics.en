---
title: ActivityMap.link
description: Customize how Activity Map collects the link clicked.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
TQID: 'https://experienceleague.adobe.com/5NCARDGth07l5vixudVzLrE7FVrh82PS4xNrJ61gnow'
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
# ActivityMap.link

The `ActivityMap.link` variable allows you to override the logic that Activity Map uses to set link values. This variable is useful in areas where you want to have more control than what [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md) provides.

>[!CAUTION]
>This variable completely overrides Activity Map logic. Setting an override function here that returns incorrect values can cause data collection issues with Activity Map dimensions and the Activity Map overlay.

## Overriding link values using the Web SDK

You can use [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) callback to alter the Web SDK payload or abort sending data.

## Link override using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## ActivityMap.link in AppMeasurement and the Analytics extension custom code editor

Assign this variable a function that:

* Receives the HTML element that was clicked; and
* Returns a string value. This string value is the final value used for the [Activity Map Link](/help/components/dimensions/activity-map-link.md) dimension.

If the return value is [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy), all Activity Map context data variables are cleared and no link data is tracked.

## Examples

Only use the title attribute from `<a>` tags. If the title attribute is not present, no link is tracked.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Return the manually set link name in `s.tl` if it exists, otherwise return the link URL.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

Instead of completely replacing the default link logic, you can conditionally alter it.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. If `linkName` is passed, then the method was called by `tl()`. Return what `tl()` passed in as `linkName`.
2. When called by Activity Map, a `linkName` is never passed, so call `customFunction()` with the link element. You can use any custom function that you'd like to return a value.
3. If neither of the above return values, use the link name normally collected as a fallback.
