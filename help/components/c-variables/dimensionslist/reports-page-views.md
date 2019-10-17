---
description: A trended report that displays the number of times your website pages were viewed for the selected time period (hour, day, week, month, quarter, or year). This report allows you to track page views for each page on your site, as well as an aggregate of page views for your entire site.
seo-description: A trended report that displays the number of times your website pages were viewed for the selected time period (hour, day, week, month, quarter, or year). This report allows you to track page views for each page on your site, as well as an aggregate of page views for your entire site.
seo-title: Page Views
solution: Analytics
title: Page Views
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
---

# Page Views

A trended report that displays the number of times your website pages were viewed for the selected time period (hour, day, week, month, quarter, or year). This report allows you to track page views for each page on your site, as well as an aggregate of page views for your entire site.

A [page view](/help/components/c-variables/c-metrics/metrics-page-view.md) is a request for a full page document rather than an element of a page, such as an image or video. For example, if a single visitor views 15 pages during a visit, 15 page views are counted. If a visitor views the same page three times during a visit, three page views are counted.

**Report Properties**

* This report references the number of times the [s.t()](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_the_s.t(.html)function) function has been called on your site. 
* Custom [link tracking](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linktracking.html) calls (such as custom links, file downloads, and exit links) use the [!DNL s.tl()] function and are not counted in this report. 

* Because image requests are sent when the user refreshes the page or clicks the back button, this report also includes these actions. 
* Hourly breakdowns are based on the report suite's time zone. 
* This report does not contain line items. As such, the report can be viewed only in trended format. 
* Granularity of hour, day, week, month, quarter, and year can be applied. That granularity is available depending on the reporting date range.

**Product-Specific Information** 

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Site Content</span> &gt; <span class="uicontrol"> Page Views</span> </p> <p>This report can use segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> Breaks down each item in this report by all other reports and variables, allowing you to see breakdowns by any granularity. </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">You can use all conversion and traffic metrics in this report, as well as different allocation for all conversion metrics. </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">This report can use multiple highly advanced segments. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

