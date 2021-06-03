---
description: You can differentiate links by customizing the link ID using the s_objectID variable, by customizing the region, and by customizing the AppMeasurement ActivityMap module file.
title: Differentiate links that reference the same Link ID and region
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
---
# Differentiate links that reference the same Link ID and region

You can differentiate links by customizing the link ID using the s_objectID variable, by customizing the region, and by customizing the AppMeasurement ActivityMap module file .

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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td> 
   <td colname="col3">
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td>
  </tr>
 </tbody>
</table>

How can you customize your web page and tagging to differentiate the values of these links? You have three options: You can customize the Link ID, or customize the region, or customize the AppMeasurement ActivityMap Module file.

## Customize the Link ID Using s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

By creating a unique object ID, `s_objectID`, for a link or link location on a page, you can either improve Activity Map tracking or use Activity Map to report on a link type or location, rather than the link URL. Click [here](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) for more information on the `s_objectID` variable.

>[!IMPORTANT]
>
>Note that a trailing semicolon (`;`) is required when using `s_objectID` in Activity Map.
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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
    &nbsp;<br/>
    &nbsp;<br/>
    Product1<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Product2<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Product3<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td> 
   <td colname="col3">
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    recommendation panel<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td>
  </tr>
 </tbody>
</table>

## Customize the Region {#section_6B1EF302573B445DBAF44176D0A12DB9}

You can customize the region by ensuring that each "Buy" link has its own Region defined. To do so, add an `"id"` parameter to one of the parents of each "Buy" anchor tag.

>[!NOTE]
>
>>You are not strictly limited to the `"id"` parameter as a region identifier. You can also set your own identifier using the JavaScript variable `"s.ActivityMap.regionIDAttribute"`.
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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    Buy<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td> 
   <td colname="col3">
    &nbsp;<br/>
    &nbsp;<br/>
    region a<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    region b<br/>
    &nbsp;<br/>
    &nbsp;<br/>
    region c<br/>
    &nbsp;<br/>
    &nbsp;<br/>
   </td>
  </tr>
 </tbody>
</table>

## Customize the AppMeasurement ActivityMap Module file {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Make sure you test the modified code to ensure that it works properly. Adobe is not responsible for how the modified code behaves.

Here are a couple of examples of **generic** link/region functions you could include (in modified form) in your AppMeasurement.js file.

```
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

The `linkName` is passed during calls to `s.tl()`.

```
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
