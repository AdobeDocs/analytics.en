---
description: This section is intended for Adobe Analytics Administrators. It focuses on the new link tracking parameters and how they ensure link uniqueness and consistency across browsers and devices, and improve the handling of link repositioning on a page.
title: Link tracking methodology
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: Business Practitioner, Administrator
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

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Name </th> 
   <th colname="col2" class="entry"> Example </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> Defaults to the "id" parameter. You can set this to another parameter. </td> 
   <td colname="col3"> String that identifies the tag attribute to use as region ID from some ancestor (parent, parent.parent, ...) element of s.linkObject, i.e. <b>the element that was clicked</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;linkId;</code><br/>
    <code>&nbsp;&nbsp;if&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A')&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title');</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;return&nbsp;linkId;</code><br/>
    <code>}</code> </td>
   <td colname="col3"> Function that receives the clicked HTMLElement and should return a string value that represents <b>the link that was clicked</b>. <br/>
     &nbsp;<br/>
     If the return value is false (null, undefined, empty string, 0), no link is tracked. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
        <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;regionId,&nbsp;className;</code><br/>
    <code>&nbsp;&nbsp;while&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement&nbsp;=&nbsp;clickedElement.parentNode))&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(regionId)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;regionId.toLowerCase();</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>}</code> </td> 
   <td colname="col3"> Function that receives the clicked HTMLElement and should return a string value that represents <b>the region where the link was found when clicked</b>. <br/>
     &nbsp;<br/>
     If the return value is false (null, undefined, empty string, 0), no link is tracked. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
     <code>//&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class</code><br/>
    <code>&lt;style&gt;</code><br/>
    <code>.linkExcluded&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;display:&nbsp;block;</code><br/>
    <code>&nbsp;&nbsp;height:&nbsp;1px;</code><br/>
    <code>&nbsp;&nbsp;left:&nbsp;-9999px;</code><br/>
    <code>&nbsp;&nbsp;overflow:&nbsp;hidden;</code><br/>
    <code>&nbsp;&nbsp;position:&nbsp;absolute;</code><br/>
    <code>&nbsp;&nbsp;width:&nbsp;1px;</code><br/>
    <code>}</code><br/>
    <code>&lt;/style&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> String that receives a comma-separated list of strings to search for in link text. If found, then the link is excluded from being tracked by Activity Map. If not set, there is no attempt made to stop tracking the link by Activity Map. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap</code><br/>
    <code>&lt;div&nbsp;id="links-included"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;div&nbsp;id="links-excluded"&gt;&nbsp;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> String that receives a comma-separated list of strings to search for in region text. If found, then the link is excluded from being tracked by Activity Map. If not set, there is no attempt made to stop tracking the link by Activity Map. </td>
  </tr>
 </tbody>
</table>
