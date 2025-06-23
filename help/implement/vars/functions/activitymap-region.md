---
title: ActivityMap.region
description: Customize how Activity Map collects the region clicked.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
---
# ActivityMap.region

The `ActivityMap.region` variable allows you to override the logic that Activity Map uses to set region values. This variable is useful in areas where you want to have more control than what [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md) provides.

>[!CAUTION]
>This variable completely overrides Activity Map logic. Setting an override function here that returns incorrect values can cause data collection issues with Activity Map dimensions and the Activity Map overlay.

## Overriding region values using the Web SDK

You can use [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) callback to alter the Web SDK payload or abort sending data.

## Region override using the Adobe Analytics extension

There is not a dedicated field in the Adobe Analytics extension to use this variable. Use the custom code editor, following AppMeasurement syntax.

## ActivityMap.region in AppMeasurement and the Analytics extension custom code editor

Assign this variable a function that:

* Receives the HTML element that was clicked; and
* Returns a string value. This string value is the final value used for the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension.

If the return value is [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy), all Activity Map context data variables are cleared and no link data is tracked.

## Examples

Use a lowercase tag name as region:

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Use specific desired class names as region:

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
