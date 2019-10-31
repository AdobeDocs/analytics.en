---
description: Displays on average how far within a visit each value was fired. This metric is valuable in determining how far within a visit your audience reaches a given page or prop value. Average Page Depth is available on any variable with pathing enabled.
seo-description: Displays on average how far within a visit each value was fired. This metric is valuable in determining how far within a visit your audience reaches a given page or prop value. Average Page Depth is available on any variable with pathing enabled.
seo-title: Average Page Depth
solution: Analytics
title: Average Page Depth
topic: Metrics
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
---

# Average Page Depth

Displays on average how far within a visit each value was fired. This metric is valuable in determining how far within a visit your audience reaches a given page or prop value. Average Page Depth is available on any variable with pathing enabled.

For example, if a visit contains the following path: Page A > Page B > Page C > Page D > Page E > Page F, the depth is an index of where the page is. For example, "Page A" has a depth of 0, while "Page F." has a depth of five. The average is based on a combination of all visits. A page depth with a value of less than one (such as 0.9) is the mean value of all pages visited prior to the page in question.

[!UICONTROL Page Depth] helps you understand where a given page typically falls in a user path, regardless of previous or next pages in this path. As such, it helps to provide insight into how the page fits into the overall picture of the user's experience on your site. This insight can be best seen on a [!UICONTROL Pages] report.

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uses </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Traffic </td> 
   <td colname="col2"> <p>The calculation of page events and pages viewed divided by visits, showing the average click number of a page. Consider the same visit path: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>The click number is calculated for every page and page event, including reloads when "Count Repeat Instances" option is enabled (this is on by default in Ad hoc analysis, and is always on in Marketing Reports and Analytics). In this visit, page A receives the click number of 0. For page B, the click numbers would be 1, 2, and 5. The calculation for the average would be [(1+2+5) / 3] for a 2.67 Average Page Depth for page B. </p> <p>When the "Count Repeat Instances" option is disabled, page B receives 1 and 4. The second will not be counted. The calculation would be [(1+4) / 2 = 2.5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversion </td> 
   <td colname="col2"> N/A </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Page Depth Report](/help/components/c-variables/dimensionslist/reports-page-depth.md)
