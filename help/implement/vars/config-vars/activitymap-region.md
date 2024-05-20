### `s.ActivityMap.region`

 Function that receives the clicked HTMLElement and should return a string value that represents **the region where the link was found when clicked.** If the return value is false (null, undefined, empty string, 0), no link is tracked. 
 
**Example**

```js
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```