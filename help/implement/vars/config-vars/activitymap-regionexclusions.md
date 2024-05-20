### `s.ActivityMap.regionExclusions`

String that receives a comma-separated list of strings to search for in region text. If found, then the link is excluded from being tracked by Activity Map. If not set, there is no attempt made to stop tracking the link by Activity Map. 

**Example**

```html
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
