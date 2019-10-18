---
description: You can use the s.tl() function to track custom elements and to configure overlay rendering for dynamic content.
seo-description: You can use the s.tl() function to track custom elements and to configure overlay rendering for dynamic content.
seo-title: Use the s.tl() function
solution: Analytics
title: Use the s.tl() function
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
---

# Use the s.tl() function

You can use the s.tl() function to track custom elements and to configure overlay rendering for dynamic content.

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [s.tl() function](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html) as part of the [!DNL Activity Map] AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. Using s.tl, you can track any custom elements that do not result in a page load.

In the s.tl function, the linkName parameter that is currently used to identify the exit links, custom links, etc. is now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

In other words, if you use s.tl to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the s.tl function. It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element’s on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. Example:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

Whenever any web page content is added to the page after the initial page load, the s.tl function is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. Then a new link collection process is triggered from [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element’s on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. Here is an example where the s.tl() function is called indirectly:

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. Here’s an example:

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

Here, we have overridden the ActivityMap.link function to do one of three things when called:

1. If linkName is passed, this is called by s.tl(), so just return what s.tl passed in as linkName. 
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. This means that when s.tl is called, we track the string returned by makeLinkName. When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link. 
1. The final solution is just to return the original return value of the default ActivityMap link function. Keeping this reference around to call in the default case helps you to only have to override or write custom code for makeLinkName and not to have to come up with a link return value for all the links on the page.
