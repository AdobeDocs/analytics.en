---
description: This section is intended for Adobe Analytics Administrators. It focuses on the new link tracking parameters and how they ensure link uniqueness and consistency across browsers and devices, and improve the handling of link repositioning on a page.
title: Link tracking methodology
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
---
# Link tracking methodology

This section is intended for Adobe Analytics Administrators. It focuses on the new link tracking parameters and how they ensure link uniqueness and consistency across browsers and devices, and improve the handling of link repositioning on a page.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). For more information on how Activity Map may be collecting PII data, go [here](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map bases its link tracking on these two IDs:

* Primary ID: this is the recognizable parameter of the link.
* Link Region: this is a secondary parameter that allows users to specify a string that is representative of the overall link area in the page or region. This parameter can be automatically generated if it is not provided by the user.

## Primary ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

If the HTML has an s_objectid, then the primary ID is defaulted to the s_objectid. Otherwise, the following parameters are used as primary ID (in this order of priority):

* Innertext 
* Alttext 
* Title 
* Src 
* Action

## Using InnerText versus using Link Action (URL) {#section_70C3573E22274522A8CC035BF18EC468}

Link action is the action taken by the web page when the link is clicked - usually the URL that is visited after clicking the link. Some of the issues you might run into when using Link Action are:

* having two or more distinct links with the same ID 
* readability of the link 
* one link with multiple actions (depending on the device where you are viewing the link)

As a result, we use InnerText with these benefits over using Link Action (URL):

* It is a good representation of the Link identity. Primary ID duplication is significantly reduced as it is not common to have multiple links with the same text.
* It ensures consistency of the Primary ID across devices and browser types.
* It is not affected by a link repositioning on the page.
* It improves readability, so users can start analyzing Link tracking reports outside Activity Map.

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

This new attribute allows users to specify a string that is representative of the page region where the link is located.

For example, for a "Contact Us" link that is located in the menu section of the web page, the user may want to pass a "Menu" region parameter. Similarly, for a "Contact Us" link located in the footer of the web page, the region parameter may be set to "footer".

The Link Region value is not set on the link itself, but on one HTML element up the DOM HTML tree that encompasses that region.
Using Link Region has these benefits:

* It helps differentiate links with the same primary ID.
* Trending on a region is less affected by the dynamic aspect of the web page.
* Users can see the top performing links within a region. With Region as an anchor, we can show overlays of links that are not currently visible on the page (Ajax, Targeting).
* A Region can supersede pages as a given region may be used across many web pages. It helps answer questions like: "Does my "Product Offering" region perform best on the Women's Landing Page or the Men's Landing Page? 
* In itself, Region is a relevant dimension to analyze highly dynamic web pages. This is because it removes the noise due to continuously changing links: a "Latest News" Region in the CNN landing page may have a lot of changing links. But the region will always be there. So it might be interesting to trend at the Region level over many days.

**Customized Region Tracking**

You can customize the Region parameter for a link (default is link ID): A tag set to "ID" will use all HTML elements with an "id" parameter as a Region. Hence, setting the Region tag to "id" will most likely return a lot of distinct regions (as many as there are different "IDs" on the page). Alternatively, if you want a more customized implementation, you can set the region tag to something more specific, such as "region_id".

Below, you can view some sample HTML using the default region ID attribute, "id".

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

If you want, you can tag elements with an arbitrary string identifier, in this case "lpos", and then add attributes with the name "lpos".

```
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
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Configuration variables {#configuration-vars}

Note that these variables are listed for reference purposes only. Activity Map should be configured properly out of the box, but you can customize your implementation using these variables.

### `s.ActivityMap.regionIDAttribute`

String that identifies the tag attribute to use as region ID from some ancestor (parent, parent.parent, ...) element of `s.linkObject`, i.e., **the element that was clicked**.

**Example**

Defaults to the "id" parameter. You can set this to another parameter.

### `s.ActivityMap.link`

Function that receives the clicked `HTMLElement` and should return a string value that represents the link that was clicked. If the return value is false (null, undefined, empty string, 0), no link is tracked.

**Example**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

 Function that receives the clicked HTMLElement and should return a string value that represents **the region where the link was found when clicked.** If the return value is false (null, undefined, empty string, 0), no link is tracked. 
 
**Example**

```
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
 
### `s.ActivityMap.linkExclusions`
  
String that receives a comma-separated list of strings to search for in link text. If found, then the link is excluded from being tracked by Activity Map. If not set, there is no attempt made to stop tracking the link by Activity Map. 

**Example**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

String that receives a comma-separated list of strings to search for in region text. If found, then the link is excluded from being tracked by Activity Map. If not set, there is no attempt made to stop tracking the link by Activity Map. 

**Example**

```
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
