---
title: ActivityMap.regionIDAttribute
description: Change the attribute that Activity Map looks for to determine region.
feature: Variables
role: Admin, Developer
---
# ActivityMap.regionIDAttribute

The `ActivityMap.regionIDAttribute` variable lets you add an attribute that Activity Map looks for when determining the [Activity Map Region](/help/components/dimensions/activity-map-region.md) dimension. 

String that identifies the tag attribute to use as region ID from some ancestor (parent, parent.parent, ...) element of `s.linkObject`, i.e., **the element that was clicked**.

**Example**

Defaults to the "id" parameter. You can set this to another parameter.

**Customized Region Tracking**

You can customize the Region parameter for a link (default is link ID): A tag set to "ID" will use all HTML elements with an "id" parameter as a Region. Hence, setting the Region tag to "id" will most likely return a lot of distinct regions (as many as there are different "IDs" on the page). Alternatively, if you want a more customized implementation, you can set the region tag to something more specific, such as "region_id".

Below, you can view some sample HTML using the default region ID attribute, "id".

```html
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

If you want, you can tag elements with an arbitrary string identifier, in this case "lpos", and then add attributes with the name "lpos".

```html
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```