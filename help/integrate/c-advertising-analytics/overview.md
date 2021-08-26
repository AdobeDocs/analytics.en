---
description: Discover everything you can do with Advertising Analytics in this detailed guide, including permissions required, and available dimensions and metrics.
title: A Guide to Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
---
# A guide to Advertising Analytics

Advertising Analytics lets you see all your Google and Bing Paid Search data side by side, within Adobe Analytics. Previously, any Google AdWords/DFA or Microsoft Bing Ads data would have to be viewed in Adobe Advertising Cloud (AMO) or in Google/Bing. You will now get the following data within Adobe Analytics: Impressions, Clicks, Costs data directly from the search engines as well as a AMO ID Instances (Click Instances). Quality Score and Average Positions will no longer be collected as Google has depericated these metrics in Sept 2019. 

>[!NOTE]
>
>Yahoo Gemini was absorbed by Microsoft Bing on March 31, 2019. As a result, the Yahoo Gemini advertising account option is no longer available.

By bringing the data from these search engines together in Adobe Analytics, you can analyze that same data by using the power of Analysis Workspace. A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

This integration is aimed at the following audiences:

* The **Analyst** who needs to collect performance reports for the Paid Search Marketer.
* The **Paid Search Marketer** who seeks answers to these questions: How much traffic am I sending to our site and are customers converting? What are my cost effective ad campaigns?

## Prerequisites {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* This functionality is available for non-Advertising Cloud and non-AMO customers.
* You must be an Adobe Analytics Administrator to have access to Advertising Analytics. Subsequently, you can [grant access permissions](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) to non-admins.
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* You need login credentials for a user with edit permissions to the search account/s which you want to integrate with Adobe Analytics, such as a Google Account ID and password.
* In the case of Bing Ads, you also need the Bing Customer ID.
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. Use other web browsers instead.

## Advertising Analytics Permissions {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics has two permissions that are automatically granted to Analytics Admins. Admins can then choose to grant these permissions to non-admins.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Permission </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Grant permission within Adobe Analytics </th> 
   <th colname="col4" class="entry"> Grant permission if you are logged in to Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics Management </p> </td> 
   <td colname="col2"> <p>Lets users set up/edit/view advertising search accounts. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> All admin </span>  &gt; <span class="uicontrol"> User management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Edit All Report Access</span> &gt; <span class="uicontrol"> Customize Analytics Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Management</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Log in to adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Products</span> &gt; <span class="uicontrol"> Product Profile</span> &gt; <span class="uicontrol"> Permissions tab</span> &gt; <span class="uicontrol"> Analytics Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Management</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics Configuration </p> </td> 
   <td colname="col2"> <p>Lets users configure report suites to be provisioned for Advertising Analytics. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> All admin </span>  &gt; <span class="uicontrol"> User management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Edit All Report Access</span> &gt; <span class="uicontrol"> Customize Report Suite Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Configuration</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Log in to adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Products</span> &gt; <span class="uicontrol"> Product Profile</span> &gt; <span class="uicontrol"> Permissions tab</span> &gt; <span class="uicontrol"> Report Suite Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Configuration</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics Dimensions and Metrics {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics adds the following dimensions and metrics to Analysis Workspace, Reports & Analytics, Report Builder, and the Analytics Reporting API.

**Dimensions**

>[!IMPORTANT]
>
>This integration creates a new set of dimensions through classifications of the AMO ID variable. These new dimensions do not impact or modify your existing marketing channels or campaign tracking variable dimensions. The AMO ID is connected to a visitor's profile when a visitor land on the site from a paid search ad. As such, the AMO dimensions can be used to break down both the AMO metrics provided by this integration as well as any data captured downstream by the visitor (visits, visitors, page views, bounce rate, orders, revenue, custom events, etc). They can also be broken down by other dimensions when reporting on other onsite metrics.
>
>The classifications for these metrics are updated daily. As such, if you make changes to the meta data in a search engine, you may not see those changes reflect until the following day when the classifications are updated.

| Classification (Dimension) Name | Definition |
|--- |--- |
| Keyword MatchType (AMO ID) | The keyword match type. Values typically will be either broad, phrase, exact, or no value if the Ad type does not have a match type. |
| Ad Platform (AMO ID) | The search engine name. Values can include Google AdWords or Microsoft Bing Ads. |
|Account (AMO ID)|The name of the search engine account that is being tracked.|
|Campaign (AMO ID)|The name of the campaign in your search engine account.|
|Ad Group (AMO ID)|The name of the ad group in your search engine campaigns.|
|Ad (AMO ID)|The Ad Title + Ad Description that is used on your ad.|
|Keyword (AMO ID)|The Keyword value from you search engine account|
|Match Type (AMO ID)|The Keyword Match Type assigned to your keyword. Values typically will be either broad, phrase, exact, or no value if the Ad type does not have a match type.|
|Ad Type (AMO ID)|The type of ad being served, which is typically "Text Ad".|
|Ad Title (AMO ID)|The Title object used in your Ad.|
|Ad Description (AMO ID)|The Ad Description object used in your Ad.|
|Ad Display URL (AMO ID)|The Ad Display URL object used in your Ad.|
|Ad Destination URL (AMO ID)|The landing page URL or Final URL assigned to your Ad.|
|Network (AMO ID)|The network the Ad is being served on. For Advertising Analytics, this value is always "Search".|
|Placement (AMO ID)|The managed placement website (for content networks). Only managed placements use this dimension.|
|Product Target (AMO ID)|The name of product target used on PLA ads (not the actual product purchased).|
|Optimization (AMO ID)|This is not used by Advertising Analytics. It is used only by Advertising Cloud customers.|
|Device (AMO ID)|Not used today. Placeholder for potential future product enhancement to indicated target device type (e.g. mobile, desktop) of ad (not the actual device of visitor).|

**Metrics**

>[!IMPORTANT]
>
>The metrics provided by Advertising Analytics (listed below) are summary-level data from the search engines. They are not connected to the Analytics visitor profiles. They are only connected to the AMO ID variable and its associated classification dimensions. As such, they should not be reported on by any dimensions/segments other than those based on the AMO ID dimensions. Doing so will result in Analytics displaying zeros for the data. You can include them in calculated metrics with other metrics, but these calculated metric should also be broken down only by the AMO ID dimensions.
>
>These metrics are data sourced on a daily basis so they will not have data for the current day. They also should not be reported on a granularity lower than daily.
>
>There is an AMO ID Instances metric that is set when the AMO ID is set on a landing page (i.e. a Clickthrough). This metric is captured in real time with the landing page hit and is available for breakdowns with other dimensions also set on the landing page.

| Metric Name | Definition |
|--- |--- |
|AMO Impressions|The number of ad impressions as reported by the search engine.|
|AMO Clicks|The number of clicks on ads as reported by the search engine.|
|AMO Cost|The cost paid for each keyword/ad as reported by the search engine.|
