---
description: Displays data about visitor location. GeoSegmentation reports include Countries, Regions, Cities, U.S. States, and U.S. DMA (digital marketing area). GeoSegmentation reports are enabled for all customers.
title: GeoSegmentation
topic: Reports
uuid: 66aa22c4-dcbc-491a-b23c-0c3d87444d23
---

# GeoSegmentation

Displays data about visitor location. GeoSegmentation reports include Countries, Regions, Cities, U.S. States, and U.S. DMA (digital marketing area). GeoSegmentation reports are enabled for all customers.

All metrics that are available to you elsewhere in Reports & Analytics are automatically included in the Countries, Regions, Cities, U.S. States, and DMA reports: conversion and visit-based metrics as well as calculated metrics. For more information, see this Adobe [blog](https://blogs.adobe.com/digitalmarketing/analytics/introducing-new-metrics-in-geosegmentation-and-more/) post.

<table id="table_566CFFC82E1149D8BAFE6641627FCF1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Report </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Countries </td> 
   <td colname="col2"> <p> The largest geographic division. In addition to the standard Ranked and Trended views available on most reports, there is also a Map view that color-codes the countries according to their relative contribution to your total traffic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Regions </td> 
   <td colname="col2"> <p> A geographic area that is smaller than a country but larger than a city. In some countries, a region is a state, province, or prefecture. In other areas, it is a constituent country, department, or metropolitan region. To the right of each region shown, the country of the region is also shown in parentheses. </p> <p>In the table detail, click Run a Cities Report for this Region (the magnifying glass) to run a report that shows how the cities in a selected region performed compared to other cities in the region. </p> <p>See <a href="/help/components/c-variables/dimensionslist/reports-geosegmentation-reference.md"  > GeoSegmentation Regions and Postal Code usage by Country</a> to see which countries use regions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cities </td> 
   <td colname="col2"> <p> The smallest geographic division. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. States </td> 
   <td colname="col2"> <p> A heat map showing visitors to each state of the United States. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> U.S. DMA </td> 
   <td colname="col2"> <p> (Digital marketing area) Media market divisions for radio and television throughout the United States. You can filter the report to show only marketing areas within a particular state. This data is provided via a partnership between Adobe and Nielsen Media Research, Inc. </p> <p>Note:  The Unspecified entry in the U.S. DMA report indicates visitors that could not be associated with a specific DMA. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report Accuracy </td> 
   <td colname="col2"> <p>Adobe has partnered with Digital Envoy, a leading provider of IP intelligence and authentication solutions, to offer GeoSegmentation, a geographical measurement capability based on end users' IP addresses. While accuracy based on individual data sets may vary, generally Digital Envoy offers over 99% accuracy at the country level, over 97% accuracy at the region level, and over 90% accuracy at the city level. </p> <p>Note: These numbers assume that <a href="/help/admin/admin/general-acct-settings-admin.md">the setting</a> to remove the last octet of the IP address is NOT enabled. </p> <p>IP addresses are mapped to postal codes, and each city is defined by the postal codes that the "local authority" defines as part of that city. For example, Berlin's suburbs are not included in the definition of Berlin, but each town/city is listed separately, assuming the IP addresses can be mapped accurately to a postal code in one of those towns. </p> <p>Some factors which may influence GeoSegmentation data include: </p> 
    <ul id="ul_1B05024AD5174232A8DB8145753FB09B"> 
     <li id="li_C3A21E7C1186490EB9A236634DB45E7F">IP addresses that represent corporate proxies. These can appear as traffic coming through the user's corporate network, which may actually be a different location if the user is working remotely. </li> 
     <li id="li_56FC36B3598C420F9246D4E8772822A7">Mobile IP addresses. Mobile IP targeting works at varying levels depending on the location and the network. A number of carriers backhaul IP traffic through centralized or regional POPs. </li> 
     <li id="li_C1EED854AE584489BCBC2A7AA20B8EF1">IP addresses belonging to users of satellite ISPs. Identifying the specific location of these users is difficult, as they usually appear to come from the location of the uplink. </li> 
     <li id="li_A735756F39554DF19E05D251CA614F02">Military and government IPs. This often represents personnel traveling around the globe and entering through their home location, rather than the base or office where they are currently stationed. </li> 
     <li id="li_ACFF1B8094684173B8325A44304CA32B">Our GeoSegmentation/IP data is provided by a 3rd-party vendor and is updated regularly based on information provided by ISPs and other network sources. IP lookups are inherently volatile, because they are bought and sold frequently all over the world. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

