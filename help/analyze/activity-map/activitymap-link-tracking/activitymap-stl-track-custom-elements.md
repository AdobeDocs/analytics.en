---
title: Use the tl() method with Activity Map
description: You can use the tl() method to track custom elements and to configure overlay rendering for dynamic content.
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
---
# Use the `tl()` method with Activity Map

You can use the `tl()` method to track custom elements and to configure overlay rendering for dynamic content.

## Tracking custom elements

Using the [`tl()` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Using `tl()`, you can track any custom elements that do not result in a page load.

In the `tl()` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. is now also used to identify the Link ID for the Activity Map variable.

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

In other words, if you use `tl()` to track your custom elements, the link ID is pulled from the value passed as the third parameter (Link name) in the `tl()` method. It is not pulled from the standard link tracking algorithm that is used for [default tracking](activitymap-link-tracking-methodology.md) in Activity Map.

## Overlay rendering for dynamic content

When the `tl()` method is called directly from the HTML element's on-click event, Activity Map can display an overlay for that element when the web page is loaded. Example:

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl()` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. Then a new link collection process is triggered from Activity Map.

When the `tl()` method is not called directly from the HTML element's on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl()` method is called indirectly:

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

The best way for Activity Map to overlay dynamic content links is to have a customized `ActivityMap.link` function set up to call the same function whose return value is passed to `tl()`. For example:

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

Here, we have overridden the `ActivityMap.link` function to do one of three things when called:

1. If `linkName` is passed, then this was called by `tl()`, so just return what `tl()` passed in as `linkName`.
2. When called by Activity Map at reporting time, a `linkName` is never passed, and so call `makeLinkName()` with the link element. This is the crucial step here - the `makeLinkName(element)` call should be the same as the `tl()` call's 3rd argument in the `<button>` tag. This means that when `tl()` is called, we track the string returned by `makeLinkName()`. When Activity Map reports on the links on the page, it uses the same call to make a link.
3. The final solution is just to return the original return value of the default ActivityMap link function. Keeping this reference around to call in the default case helps you to only have to override or write custom code for `makeLinkName()` and not to have to come up with a link return value for all the links on the page.
