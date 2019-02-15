---
description: The table below displays variable to report mapping for the variables used to populate Analytics reports.
keywords: Analytics Implementation
seo-description: The table below displays variable to report mapping for the variables used to populate Analytics reports.
seo-title: Variable to report mapping
solution: Analytics
title: Variable to report mapping
topic: Developer and implementation
uuid: fd81f97d-dd1a-47d5-9157-b7932fe13490
---

# Variable to report mapping

The table below displays variable to report mapping for the variables used to populate Analytics reports.

Each variable is listed with the reports that use the variable listed next to it. 

<table id="table_16443E46AC0E46509F8533D26EDE1BCC"> 
 <thead> 
  <tr> 
   <th class="entry"> Variable </th> 
   <th class="entry"> Reports Populated </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> s.pageName </td> 
   <td> <p>Conversion Reports &gt; Path Reports &gt; Page Value </p> <p>Conversion Reports &gt; Path Reports &gt; Entry Page </p> <p>Conversion Reports &gt; Path Reports &gt; Original Entry Pages </p> <p>Traffic Reports &gt; Site Traffic &gt; Page Views </p> <p>Traffic Reports &gt; Site Traffic &gt; Hourly Unique Visitors </p> <p>Traffic Reports &gt; Site Traffic &gt; Daily Unique Visitors </p> <p>Traffic Reports &gt; Site Traffic &gt; Monthly Unique Visitors </p> <p>Traffic Reports &gt; Site Traffic &gt; Yearly Unique Visitors </p> <p>Traffic Reports &gt; Visitor Profile &gt; Pages Viewed by Key Visitors </p> <p>Traffic Reports &gt; Segmentation &gt; Most Popular Pages </p> <p>Path Reports &gt; Pages &gt; Page Summary </p> <p>Path Reports &gt; Pages &gt; Page Value </p> <p>Path Reports &gt; Pages &gt; Most Popular Pages </p> <p>Path Reports &gt; Pages &gt; Reloads </p> <p>Path Reports &gt; Pages &gt; Click to Page </p> <p>Path Reports &gt; Pages &gt; Time Spent on Page </p> <p>Path Reports &gt; Entries &amp; Exits &gt; Entry Pages </p> <p>Path Reports &gt; Entries &amp; Exits &gt; Exit Pages </p> <p>Path Reports &gt; Entries &amp; Exits &gt; Exit Links </p> <p>Path Reports &gt; Complete Paths &gt; Full Paths </p> <p>Path Reports &gt; Complete Paths &gt; Longest Paths </p> <p>Path Reports &gt; Complete Paths &gt; Path Length </p> <p>Path Reports &gt; Complete Paths &gt; Time Spent per Visit </p> <p>Path Reports &gt; Complete Paths &gt; Single-page Visits </p> <p>Path Reports &gt; Advanced Analysis &gt; Previous Page </p> <p>Path Reports &gt; Advanced Analysis &gt; Next Page </p> <p>Path Reports &gt; Advanced Analysis &gt; Previous Page Flow </p> <p>Path Reports &gt; Advanced Analysis &gt; Next Page Flow </p> <p>Path Reports &gt; Advanced Analysis &gt; PathFinder </p> <p>Path Reports &gt; Advanced Analysis &gt; Fall-out </p> <p> <b>NOTE:</b> In all of the <span class="wintitle"> Traffic</span> Reports listed above, with the exception of the <span class="wintitle"> Most Popular Pages</span> Report, if the <span class="wintitle"> s.pageName</span> variable is not set, the URL is used. </p> </td> 
  </tr> 
  <tr> 
   <td> s.server </td> 
   <td> Traffic Reports &gt; Segmentation &gt; Most Popular Servers </td> 
  </tr> 
  <tr> 
   <td> s.pageType </td> 
   <td> Path Reports &gt; Pages &gt; Pages Not Found </td> 
  </tr> 
  <tr> 
   <td> s.channel </td> 
   <td> <p>Conversion Reports &gt; Site Path Reports &gt; Site Section </p> <p>Traffic Reports &gt; Segmentation &gt; Most Popular Site Sections </p> </td> 
  </tr> 
  <tr> 
   <td> s.prop1 - s.prop20 </td> 
   <td> Traffic Reports &gt; Custom Insight &gt; Custom Insight 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.campaign </td> 
   <td> <p>Conversion Reports &gt; Campaigns &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Campaigns &gt; Tracking Code </p> </td> 
  </tr> 
  <tr> 
   <td> s.state </td> 
   <td> Conversion Reports &gt; Visitor Profile &gt; States </td> 
  </tr> 
  <tr> 
   <td> s.zip </td> 
   <td> Conversion Reports &gt; Visitor Profile &gt; ZIP/ Postal Codes </td> 
  </tr> 
  <tr> 
   <td> s.events </td> 
   <td> <p>Conversion Reports &gt; Purchases &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Purchases &gt; Revenue </p> <p>Conversion Reports &gt; Purchases &gt; Orders </p> <p>Conversion Reports &gt; Purchases &gt; Units </p> <p>Conversion Reports &gt; Shopping Cart &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Shopping Cart &gt; Carts </p> <p>Conversion Reports &gt; Shopping Cart &gt; Cart Views </p> <p>Conversion Reports &gt; Shopping Cart &gt; Cart Additions </p> <p>Conversion Reports &gt; Shopping Cart &gt; Cart Removals </p> <p>Conversion Reports &gt; Shopping Cart &gt; Checkouts </p> <p>Conversion Reports &gt; Custom Events &gt; Custom Event 1-20 </p> <p>Conversion Reports &gt; Products &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Products &gt; Cross Sell </p> <p>Conversion Reports &gt; Products &gt; Categories </p> <p>Conversion Reports &gt; Campaigns &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Customer Loyalty &gt; Customer Loyalty </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Before First Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Since Last Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Visit Number </p> <p>Conversion Reports &gt; Sales Cycle &gt; Daily Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Monthly Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Yearly Unique Customers </p> <p>Conversion Reports &gt; Site Path &gt; Page Value </p> </td> 
  </tr> 
  <tr> 
   <td> s.products </td> 
   <td> <p>Conversion Reports &gt; Purchases &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Purchases &gt; Revenue </p> <p>Conversion Reports &gt; Purchases &gt; Orders </p> <p>Conversion Reports &gt; Purchases &gt; Units </p> <p>Conversion Reports &gt; Shopping Cart &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Products &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Products &gt; Cross Sell </p> <p>Conversion Reports &gt; Products &gt; Categories </p> <p>Conversion Reports &gt; Campaigns &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Customer Loyalty &gt; Customer Loyalty </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Before First Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Since Last Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Visit Number </p> <p>Conversion Reports &gt; Sales Cycle &gt; Daily Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Monthly Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Yearly Unique Customers </p> <p>Conversion Reports &gt; Site Path &gt; Page Value </p> </td> 
  </tr> 
  <tr> 
   <td> s.purchaseID </td> 
   <td> <p>Conversion Reports &gt; Purchases &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Purchases &gt; Revenue </p> <p>Conversion Reports &gt; Purchases &gt; Orders </p> <p>Conversion Reports &gt; Purchases &gt; Units </p> <p>Conversion Reports &gt; Shopping Cart &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Products &gt; Conversion &amp; Averages </p> <p>Conversion Reports &gt; Products &gt; Cross Sell </p> <p>Conversion Reports &gt; Customer Loyalty &gt; Customer Loyalty </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Before First Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Days Since Last Purchase </p> <p>Conversion Reports &gt; Sales Cycle &gt; Visit Number </p> <p>Conversion Reports &gt; Sales Cycle &gt; Daily Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Monthly Unique Customers </p> <p>Conversion Reports &gt; Sales Cycle &gt; Yearly Unique Customers </p> <p>Conversion Reports &gt; Site Path &gt; Page Value </p> </td> 
  </tr> 
  <tr> 
   <td> s.eVar1 - s.eVar20 </td> 
   <td> Conversion Reports &gt; Custom Variables &gt; Customer eVar 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.linkName </td> 
   <td> Traffic Reports &gt; Custom Insight &gt; Custom Links </td> 
  </tr> 
  <tr> 
   <td> s.hier1 - s.hier5 </td> 
   <td> Traffic Reports &gt; Hierarchies &gt; Hierarchy 1-5 </td> 
  </tr> 
 </tbody> 
</table>

