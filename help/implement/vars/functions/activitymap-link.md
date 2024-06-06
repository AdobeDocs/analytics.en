---
title: ActivityMap.link
description: Customize how Activity Map collects the link clicked.
feature: Variables
role: Admin, Developer
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

If the return value is [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy), no link is tracked.

## Examples

Only use the title attribute from `<a>` tags. If the title attribute is not present, no link is tracked.

```js
function(clickedElement) {
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
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

Instead of completely replacing default link logic, you can conditionally alter it.

```js
// Copy the original link function
var originalLinkFunction = s.ActivityMap.link;
// Return the link name from s.tl, a modified activity map value, or the original activity map value
s.ActivityMap.link = function(element,linkName)
{
    return linkName || makeLinkName(element) || originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

1. If `linkName` is passed, then the method was called by `tl()`. Return what `tl()` passed in as `linkName`.
2. When called by Activity Map at reporting time, a `linkName` is never passed, so call `makeLinkName()` with the link element. This is the crucial step here - the `makeLinkName(element)` call should be the same as the `tl()` call's 3rd argument in the `<button>` tag. This means that when `tl()` is called, we track the string returned by `makeLinkName()`. When Activity Map reports on the links on the page, it uses the same call to make a link.
3. The final solution is just to return the original return value of the default Activity Map link function. Keeping this reference around to call in the default case helps you to only have to override or write custom code for `makeLinkName()` and not to have to come up with a link return value for all the links on the page.
