---
description: Displays a breakdown of search keywords.
solution: Analytics
title: Search Keywords
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
---

# Search Keywords

Displays a breakdown of search keywords.

 **Search Keywords - All**: Displays a breakdown of each search keyword that has been used to find your site. You can sort this list by page views or search keywords by clicking the column title above the listing. Click the magnifying glass next to a search keyword to see the search results for your site.

**Search Keywords - Paid**: Displays a breakdown of each paid search keyword that is used to find your site. You can sort this list by page views or search keywords by clicking the column title above the listing. Click the magnifying glass next to a search keyword to see the search results for your site.

**Search Keywords - Natural**: Displays a breakdown of each natural search keyword that is used to find your site. You can sort this list by page views or search keywords by clicking the column title above the listing. Click the magnifying glass next to a search keyword to see the search results for your site.

>[!IMPORTANT]
>
>For paid and natural search, search engines stopped providing (in most cases) the search keywords as part of the referrer. As a result, Adobe always classifies the Google (or Bing, or Yahoo) domain as search. Based on the format and contents of the referrer (even without the keywords), Adobe can determine often that it was the result of a search, so the search is counted with the Keywords Unavailable. [More...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Metric Allocation </td> 
   <td colname="col2"> <p>Original Value (default) </p> <p> Can be changed to linear. </p> </td> 
   <td colname="col3"> Most Recent (can be changed to linear using the linear version of a metic) </td> 
   <td colname="col4"> <p>Original Value (default) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Values Expire After </td> 
   <td colname="col2"> Visit - can be shortened but not lengthened </td> 
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
   <td colname="col2"> <p>"None": site wide totals that did not have a keyword during the visit. </p> "Keyword Unavailable" is searches where the keyword was removed from the search and is not sent to data collection. This typically occurs when a customer is signed in to a Google account. Applies to paid and natural. </td> 
   <td colname="col3"> (low-traffic) represents values past the first 500k that haven't received enough traffic to be reported. </td> 
   <td colname="col4"> <p> Empty - equivalent of "None", site wide totals that did not have a keyword during the visit. </p> <p>"Keyword Unavailable" is searches where the keyword was removed from the search and is not sent to data collection. This typically occurs when a customer is signed in to a Google account. Applies to paid and natural. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

|  Date  | Change  |
|---|---|
|  1/16/2014  | Data warehouse was updated to match the logic used by marketing reports & analytics. Before this date, search keywords did not persist across the visit.  |

