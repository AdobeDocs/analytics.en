---
description: You can differentiate links by customizing the link ID using the s_objectID variable, by customizing the region, and by customizing the AppMeasurement ActivityMap module file .
seo-description: You can differentiate links by customizing the link ID using the s_objectID variable, by customizing the region, and by customizing the AppMeasurement ActivityMap module file .
seo-title: Differentiate links that reference the same Link ID and region
solution: Analytics
title: Differentiate links that reference the same Link ID and region
topic: Activity map
uuid: 4f305813-5488-4a17-9405-4dd4832e7a9e
index: y
internal: n
snippet: y
translate: y
---

# Differentiate links that reference the same Link ID and region

As an example, let's say you have multiple "Buy" links that are identified by Activity Map under the same Link ID and Region: 

<table id="table_3020E2C0175D455C84E794CF51BE5A93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code sample </th> 
   <th colname="col2" class="entry"> Link ID </th> 
   <th colname="col3" class="entry"> Region </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </codeblock> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation Panel <p> </p> <p> </p> <p>recommendation Panel </p> <p> </p> <p> </p> <p>recommendation Panel </p> </td> 
  </tr> 
 </tbody> 
</table>

How can you customize your web page and tagging to differentiate the values of these links? You have three options: You can customize the Link ID, or customize the region, or customize the AppMeasurement ActivityMap Module file. 

## Customize the Link ID Using s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

By creating a unique object ID for a link or link location on a page, you can either improve Activity Map tracking or use Activity Map to report on a link type or location, rather than the link URL. Click [ here ](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) for more information on the s_objectID variable. 


>[!IMPORTANT]
>
>Note that a trailing semicolon (;) is required when using s_objectID in Activity Map.



<table id="table_9439A5F320304E439A19842CF3EBA456"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> Code Sample </th> 
   <th colname="col2" class="entry"> Link ID </th> 
   <th colname="col3" class="entry"> Region </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <codeblock>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </codeblock> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product 2 </p> <p> </p> <p> </p> <p>Product 3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Customize the Region {#section_6B1EF302573B445DBAF44176D0A12DB9}

You can customize the region by ensuring that each "buy" link has its own Region defined. To do so, add an "id" parameter to one of the parents of each "Buy" anchor tag. 

>[!NOTE]
>
>You are not strictly limited to the "id" parameter as a region identifier. You can also set your own identifier using the JavaScript variable "customRegionIDAttr?".


<table id="table_250DB52A869C466B942517BABA1C287B"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> Code Sample </th> 
   <th colname="col2" class="entry"> Link ID </th> 
   <th colname="col3" class="entry"> Region </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <codeblock>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </codeblock> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>


## Customize the AppMeasurement ActivityMap Module file {#section_B933BB9F944E4D5389002908A5A881F8}


>[!CAUTION]
>
>Make sure you test the modified code to ensure that it works properly. Adobe is not responsible for how the modified code behaves.

Here are a couple of examples of** generic** link/region functions you could include (in modified form) in your AppMeasurement.js file. 

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' &amp;&amp; ele.href){ 
return ele.href; 
} 
} 
} 

```
The linkName is passed during calls to s.tl. 

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele &amp;&amp; (ele = ele.parentNode))){ 
if( (className=ele.className) &amp;&amp; classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 

```
