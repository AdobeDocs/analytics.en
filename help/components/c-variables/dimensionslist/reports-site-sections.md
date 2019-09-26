---
description: Shows the areas of your site that are accessed most by your visitors. Site Sections can include groups of products, similar to categories, which you define. For example, you might have a Cameras group of pages, a Computers group, and so on. Data for the Conversion Site Sections Report is imported from the Site Section Report in the Traffic group, which receives its information from the channel variable in the tracking code. You can use this report to identify the greatest impact on site statistics from items in varying site sections.
seo-description: Shows the areas of your site that are accessed most by your visitors. Site Sections can include groups of products, similar to categories, which you define. For example, you might have a Cameras group of pages, a Computers group, and so on. Data for the Conversion Site Sections Report is imported from the Site Section Report in the Traffic group, which receives its information from the channel variable in the tracking code. You can use this report to identify the greatest impact on site statistics from items in varying site sections.
seo-title: Site Sections
solution: Analytics
title: Site Sections
topic: Reports
uuid: 6839c566-f88f-4979-9cf5-52a77c0b0416
---

# Site Sections

Shows the areas of your site that are accessed most by your visitors. Site Sections can include groups of products, similar to categories, which you define. For example, you might have a Cameras group of pages, a Computers group, and so on. Data for the Conversion Site Sections Report is imported from the Site Section Report in the Traffic group, which receives its information from the channel variable in the tracking code. You can use this report to identify the greatest impact on site statistics from items in varying site sections.

* This report references data directly from the [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_channel.html) variable implemented on your website. 
* This report can be viewed in both trended and ranked formats. 
* This report can use a search filter to locate specific line items. 
* Classifications can be used in this report, allowing you to rename and consolidate line items. 
* Correlations can be created with any other traffic variable via Admin Tools. 
* This report can utilize the following metrics:

    * **Pageviews**: the number of times the [pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) variable or URL was defined (set as the default metric) 
    
    * **All pathing metrics**: Visits, Average Page Depth, Average Time Spent on Page, Entries, Exits, Reloads, and Single Access 
    * Depending on your organization's and report suite settings: Daily, Weekly, Monthly and Quarterly Unique Visitors can be enabled on this report. 
    * **All standard eCommerce metrics**: Revenue, Orders, Units, Carts, Cart Views, Checkouts, Cart Additions, and Cart Removals 
    * **All custom events**: Events 1-80, and Events 81-100 if on H22 code or higher.

All conversion events in the [!UICONTROL Site Sections Report] use last allocation. You will see conversion divided across pages that do not contain success events within your implementation. This is different than the [Pages Report](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), which uses linear allocation.

**Product Specific Information** 

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interface </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Site Content</span> &gt; <span class="uicontrol"> Site Sections</span> </p> <p>In addition to correlations, this report can utilize the following breakdowns: </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">Any classified reports based on this report </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> Tracking Codes Report</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> Products</span> and <span class="wintitle"> Categories</span> reports </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> Customer Loyalty Report</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">Any fully-subrelated conversion variables </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> Marketing Channels First and Last Touch</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol"> Target</span> &gt; <span class="uicontrol"> Campaigns</span> report (if enabled) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">Time Spent per visit </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">SiteSections </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">Entry Pages </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">Most Traffic Sources reports </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">Visit Number </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">Many Visitor Profile Reports </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">All conversion variables and list variables </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">Visits as well as Daily, Weekly, Monthly, Quarterly, and Arbitrary Unique Visitors are available. </li> 
      </ul> </li> 
    </ul> <p>This report can utilize segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Ad Hoc Analysis can break down the Site Sections report by essentially all other reports within the marketing report interface. </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">In addition to all previously mentioned events, can utilize all conversion and traffic metrics, as well as use different allocation for all conversion metrics. </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">This report can utilize multiple highly advanced segments. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

