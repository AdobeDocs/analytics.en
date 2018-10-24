---
description: Data Sources supports the following conversion data dimensions and metrics for data types that are processed as conversion.
seo-description: Data Sources supports the following conversion data dimensions and metrics for data types that are processed as conversion.
seo-title: Conversion
solution: Analytics
subtopic: Data sources
title: Conversion
topic: Developer and implementation
uuid: 9a4a86b6-9716-4ddc-8198-2ab44e0ee4b9
index: y
internal: n
snippet: y
---

# Conversion

Data Sources supports the following conversion data dimensions and metrics for data types that are processed as conversion.

## Conversion Dimensions and Metrics {#section_FA1731B232B246DABEDF5A5D84159084}

If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value. The number of custom events and eVar views supported by a report suite is contract-dependent, and varies between companies. 

<p class="head"> <b>Conversion Dimensions</b> </p>

<table id="table_7C7E5D97B33F4EE3988F8C032D74AFDF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column Name </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tracking Code </p> </td> 
   <td colname="col2"> <p>Tracking code name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date </p> </td> 
   <td colname="col2"> <p>Use the following date format: <span class="codeph"> MM/DD/YYYY/HH/mm/SS</span> (for example, <span class="codeph"> 01/01/2015/06/00/00</span>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Category </p> </td> 
   <td colname="col2"> <p>Category name. </p> <p>If you specify a category, then you must also select a product. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Channel </p> </td> 
   <td colname="col2"> <p>Channel name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>n</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>n</i> name. Valid values for <i>n</i> are whole number 1 - 75. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Product name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>State </p> </td> 
   <td colname="col2"> <p>State name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zip </p> </td> 
   <td colname="col2"> <p>Zip name. </p> </td> 
  </tr> 
 </tbody> 
</table>

<p class="head"> <b>Conversion Metrics</b> </p>

<table id="table_F4F2F9CA4DF849BBB7FF04C32B298D08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column Name </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Clickthroughs </p> </td> 
   <td colname="col2"> <p>Number of tracking code views. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cart Adds </p> </td> 
   <td colname="col2"> <p>Number of cart additions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cart Opens </p> </td> 
   <td colname="col2"> <p>Number of cart opens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cart Removes </p> </td> 
   <td colname="col2"> <p>Number of cart removals. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cart Views </p> </td> 
   <td colname="col2"> <p>Number of cart views. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Checkouts </p> </td> 
   <td colname="col2"> <p>Number of checkouts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event <i>n</i> </p> </td> 
   <td colname="col2"> <p>Number of times event <i>n</i> occurred. Valid values for <i>n</i> are whole number 1 - 100. </p> <p>If you specify a View event, you must also specify the corresponding data dimension (eVar). For example, if you include eVar2 views, then you must list eVar2 with a value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>n</i> Views </p> </td> 
   <td colname="col2"> <p>Number of times eVar <i>n</i> was viewed. Valid values for <i>n</i> are whole number 1 - 75. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Price </p> </td> 
   <td colname="col2"> <p>Product price. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Orders </p> </td> 
   <td colname="col2"> <p>Number of orders placed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product Views </p> </td> 
   <td colname="col2"> <p>Number of product views. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantity </p> </td> 
   <td colname="col2"> <p>Number of units sold. </p> </td> 
  </tr> 
 </tbody> 
</table>

