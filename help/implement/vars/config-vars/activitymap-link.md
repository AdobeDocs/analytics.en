### `s.ActivityMap.link`

Function that receives the clicked `HTMLElement` and should return a string value that represents the link that was clicked. If the return value is false (null, undefined, empty string, 0), no link is tracked.

**Example**

```js
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
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