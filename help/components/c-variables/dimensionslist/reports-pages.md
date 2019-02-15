---
description: Ranks the pages on your site based on the pages that receive the most traffic. If your business question deals with quantitative data for pages, you can use this report to answer that question, by adding the right metrics.
seo-description: Ranks the pages on your site based on the pages that receive the most traffic. If your business question deals with quantitative data for pages, you can use this report to answer that question, by adding the right metrics.
seo-title: Pages
solution: Analytics
title: Pages
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
---

# Pages

Ranks the pages on your site based on the pages that receive the most traffic. If your business question deals with quantitative data for pages, you can use this report to answer that question, by adding the right metrics.

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Note that in Reports & Analytics, metrics on the Pages Report use linear allocation. For example, revenue is split between all pages viewed before a purchase event. This can cause confusion for some metrics that you might expect to occur only on one page, such as a shopping cart addition. 

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Reports &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Metric Allocation </td> 
   <td colname="col2"> Linear </td> 
   <td colname="col3"> Allocation is specific to each dimension. The default is Last Touch allocation, but the 'pagename' dimension is an exception. If you apply a custom event to 'pagename', it will be Exact Hit allocation. </td> 
   <td colname="col4"> <p>Values set on the same page view </p> </td> 
   <td colname="col5"> <p>Values set on the same page view </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Values Expire After </td> 
   <td colname="col2"> Page view </td> 
   <td colname="col3"> Page view </td> 
   <td colname="col4"> Page view </td> 
   <td colname="col5"> Page view </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Value Limits </td> 
   <td colname="col2"> <p>First 500k unique per month + new values with traffic </p> </td> 
   <td colname="col3"> <p>First 500k unique per month + new values with traffic </p> </td> 
   <td colname="col4"> None </td> 
   <td colname="col5"> <p>First 500k unique per month + new values with traffic </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Special values </td> 
   <td colname="col2"> <p>(low-traffic) represents values past the first 500k that haven't received enough traffic to be reported. </p> </td> 
   <td colname="col3"> <p>(low-traffic) represents values past the first 500k that haven't received enough traffic to be reported. </p> </td> 
   <td colname="col4"> none </td> 
   <td colname="col5"> <p>(low-traffic) represents values past the first 500k that haven't received enough traffic to be reported. </p> </td> 
  </tr> 
 </tbody> 
</table>

In Reports & Analytics, if you apply any custom event as metric in a Pages report, linear allocation applies.

This means that even if the event was sent with an s.tl() call, it will get the linear allocation of any previous s.t() call. Example:

|  Page Name  | Page_event  | Events  |
|---|---|---|
|  Page1  |**s.t()** |  |
|  Page1  | s.tl()  | Event1  |
|  Page1  | s.tl()  | Event1  |
|  Page1  | s.tl()  | Event1  |
|  Page2  |**s.t()** |  |
|  Page2  |**s.t()** |  |
|  Page2  | s.tl()  | Event1  |

For this scenario, we will obtain the following allocation in the Pages report:

|  Pages  | Pageviews  | Event 1  |
|---|---|---|
|  Page 1  | 1  | 1+1+1+1/3 = 3.33  |
|  Page 2  | 2  | 2/3 = 0.67  |

Even if the event is sent on an s.tl call, the page viewed prior to the event that was sent (s.t() call) will get partial credit.

## Notes {#section_47B0F4746D4847AC9E8697127063F4D0}

* If no page name exists, the URL is used. 
* If you have a hit with no page name, page URL, or event list (no commerce event), the hit is excluded. 
* Breakdowns on pages show all pages that had a value persisted.

