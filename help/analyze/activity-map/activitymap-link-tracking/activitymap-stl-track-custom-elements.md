---
description: You can use the s.tl() method to track custom elements and to configure overlay rendering for dynamic content.
title: Use the s.tl() method
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
---

# Use the `tl()` method

You can use the `tl()` method to track custom elements and to configure overlay rendering for dynamic content.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [`tl()` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Using s.tl, you can track any custom elements that do not result in a page load.

In the `tl()` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. is now also used to identify the Link ID for the Activity Map variable.

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In other words, if you use `s.tl()` to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the `s.tl()` method. It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in Activity Map.

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element's on-click event, Activity Map can display an overlay for that element when the web page is loaded. Example:

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl()` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. Then a new link collection process is triggered from Activity Map.

When the `tl()` method is not called directly from the HTML element's on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl()` method is called indirectly:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

The best way for Activity Map to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to `s.tl`. For example:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Here, we have overridden the ActivityMap.link function to do one of three things when called:

1. If linkName is passed, this is called by s.tl(), so just return what s.tl passed in as linkName.
2. This is called by Activity Map at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the "makeLinkName(element)" call should be the same at the s.tl call's 3rd argument in the `<button>` tag. This means that when s.tl is called, we track the string returned by makeLinkName. When Activity Map reports on the links on the page, is uses the same call to make a link.
3. The final solution is just to return the original return value of the default ActivityMap link function. Keeping this reference around to call in the default case helps you to only have to override or write custom code for makeLinkName and not to have to come up with a link return value for all the links on the page.
