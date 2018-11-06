---
description: Displays the domain or URL where your visitors came from before they arrived at your site, the methods visitors use to find your website, and the number of visits to your site that came from these referring locations.
seo-description: Displays the domain or URL where your visitors came from before they arrived at your site, the methods visitors use to find your website, and the number of visits to your site that came from these referring locations.
seo-title: Referrers
solution: Analytics
title: Referrers
topic: Reports
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
index: y
internal: n
snippet: y
---

# Referrers

Displays the domain or URL where your visitors came from before they arrived at your site, the methods visitors use to find your website, and the number of visits to your site that came from these referring locations.

For example, if a visitor clicks a link from Site A and arrives at your site, Site A is the referrer if it is not defined as part of your domain. During implementation, your implementation consultant can help you to define the domains and URLs that are part of your website. (This change can be done after implementation.)

Domains or URLs that are not part of those defined domains and URLs are considered referrers. For example, web page A and web page B are added to the internal URL filter, but web page C is not. In this case, web page C is considered a referrer.

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing reports &amp; analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc analytics </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Metric Allocation </td> 
   <td colname="col2"> Most Recent </td> 
   <td colname="col3"> Most Recent </td> 
   <td colname="col4"> Most Recent </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Values Expire After </td> 
   <td colname="col2"> Visit </td> 
   <td colname="col3"> Visit </td> 
   <td colname="col4"> Visit </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Value Limits </td> 
   <td colname="col2"> No limits (might change in a future release) </td> 
   <td colname="col3"> No limits (might change in a future release) </td> 
   <td colname="col4"> none </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Special values </td> 
   <td colname="col2"> <p>"None": site wide totals that did not have a referrer during the visit. </p> </td> 
   <td colname="col3"> <p>"None": site wide totals that did not have a referrer during the visit. </p> </td> 
   <td colname="col4"> <p> Empty - equivalent of "None", site wide totals that did not have a referrer during the visit. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notes {#section_B83A3571D64E4E7792712FAF740D7955}

* The referrer, referrer type, and referring domain are set on the first hit of the visit, or during a visit when the referrer is external (for example, if a visitor leaves your site, uses a search engine, then returns to your site before the first visit expires). These values are set at the same time and persist across the visit. 
* Internal URLs are filtered. Only referrers that do not match the internal URL filters are in this report. 
* The corresponding metric is called Referrer Instance in ad hoc analysis. 
* Typed/Bookmarked values are not included on Referrers Report. This means that site wide Visits don't match visits on this report.

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Date </th> 
   <th colname="col2" class="entry"> Change </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1/16/2014 </td> 
   <td colname="col2"> Data warehouse was updated to match the logic used by marketing reports &amp; analytics. Before this date, search keywords did not persist across the visit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> Before July 2012, "None" includes all mobile traffic, Typed/Bookmarked, and visits with no JavaScript. After July 2012, "None" includes only hits with no JavaScript on the first page of visit. </p> </td> 
  </tr> 
 </tbody> 
</table>

