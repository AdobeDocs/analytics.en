---
title: ActivityMap.region
description: Customize how Activity Map collects the region clicked.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
TQID: 'https://experienceleague.adobe.com/EVVto7LRuTewu9y9AHLAPGn7sbqhJU3QSjlNtjKE5bQ'
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
