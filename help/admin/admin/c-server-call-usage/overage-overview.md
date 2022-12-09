---
description: Overview of Adobe Analytics server call usage functionality.
title: Server Call Usage Overview
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
---
# Server Call Usage Overview

## Why Monitor and Alert to Server Call Usage? {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server Call Usage addresses your requests for transparency into both browser and mobile server call usage data. It lets you access:

* A Server Call Usage dashboard that tracks your server call consumption data and compares it to your contractual limit. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

The main benefits of Server Call Usage include:

* **Visibility** into your server call consumption and commitment data, including mobile consumption vis a vis your contractual server call usage limit.
* **Alerts** to notify you of the risk or occurrence of an overage and prepare for/act on the possibility of incurring overages.

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. Further, the data did not include mobile consumption. This feature will also replace the current **[!UICONTROL Billing Information]** report under  **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** .

## Prerequisites {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Permissions:** To access the Server Call Usage Dashboard and the Alert Builder/Manager, you must be an Adobe Analytics Administrator.
* **Permissions:** Administrators can grant access to non-admins: the permission is called **[!UICONTROL Server Call Usage]**. See [Server Call Usage Permission](/help/admin/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Important Terminology {#section_CBA348A039F34563B097CD8890AB358D}

Here is a short primer on essential terminology for Server Call Usage: 

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Term </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server call </p> </td> 
   <td colname="col2"> <p>A server call, also known as a "hit" or an "image request", is an instance in which data is sent to Adobe servers to process. The most common type of server call is a page view. A page view occurs where a visitor views a page on your website and a server call is generated to Adobe, where information is collected, processed, and then included in your report metrics. </p> <p>There are other types of server calls, including exit links and file downloads, where data is sent to Adobe to process, but they are not recorded as a new page view. Even "excluded" page views (excluded from your reports by an IP address range you configure, for example) are server calls because they are received and processed by Adobe but never show up in your reports. </p> <p><b>Primary Server Call</b>: Requests received directly from website visitor browsers or the Data Insertion API. Includes Primary Hits (Page Views), Primary Custom Events, Primary Download Events, and Primary Exit Events. </p> <p><b>Secondary Server Call</b>: Copies of primary server calls created by multi-suite tags or copied/moved by a VISTA rule. If a secondary server call has been moved (not copied) to a different report suite by a VISTA rule, the accumulated secondary calls are deducted from the primary server calls. </p> <p><b>Mobile Primary Server Call </b> </p> <p>Requests received directly from one of the Mobile SDKs. Include trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Mobile Secondary Server Call</b> </p> <p>Copies of primary server calls created by multi-suite tags or copied/moved by a VISTA rule. If a secondary server call has been moved (not copied) to a different report suite by a VISTA rule, the accumulated secondary calls are deducted from the primary server calls. </p> <p>Note:  If your company is contractually entitled to only Mobile Server Calls (Primary or Secondary), both your web and mobile-specific usage will count against your Mobile-specific commitment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Billing Company (Billing ID) </p> </td> 
   <td colname="col2"> <p>The legal entity that gets billed for server calls. For example, adobe.com. Each billing company has a Billing ID that is used to uniquely identify the billing customer. A billing ID could be tied to multiple Experience Cloud Orgs; there is not always a 1:1 relationship between an org and a billing ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Login Company </p> </td> 
   <td colname="col2"> <p>One billing company can have <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html"> multiple login companies </a>. A login company is a collection of report suites used by your organization. Some organizations have multiple login companies that apply to different parts of the organization. This is especially useful for large organizations that deal with different business units where many report suites are not applicable to others in the company. </p> <p>Often, these are the regional subsidiaries of a company. This example shows login companies and their associated report suites: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Note:  Server call usage data for <u>all</u> report suites within a billing company is visible to all users with the appropriate <a href="/help/admin/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369"> permission</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud organization </p> </td> 
   <td colname="col2"> <p>An organization is the entity that enables an administrator to configure groups and users, and to control single sign-on in the Experience Cloud. The organization functions like a login company that spans all the Experience Cloud products and solutions. </p> <p>Most often, an organization is your company name. However, a company can have many organizations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Call Commitment </p> </td> 
   <td colname="col2"> <p>When your company signs a contract with Adobe, the Adobe Sales team identifies with the you, the customer, the types (Primary, Secondary, Mobile Primary, Mobile Secondary) and the approximate number of server calls that you are expecting to incur over the course of the contract period. This is your total server call commitment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage Period </p> </td> 
   <td colname="col2"> <p>For purposes of server call usage monitoring, this total server call commitment is broken down into smaller usage periods (such as 3 months) to facilitate year-over-year comparisons. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contract Period </p> </td> 
   <td colname="col2"> <p>Contract periods can go over multiple years. Let's say your company has a server call commitment of 6 million calls for a 3-year contract time. For purposes of server call usage monitoring, this 3-year period can be broken down into smaller usage periods to facilitate year-over-year comparisons. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Server Call Usage Permission {#section_FCC58EB635954A32990D4E67B52B4369}

The Server Call Usage permission is automatically granted to Analytics Admins. It lets users view the dashboard and create server call alerts. Admins can choose to grant this permission to non-admins.

>[!NOTE]
>
>Your company can choose which login companies have access to Server Call Usage.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Permission Name </th> 
   <th colname="col3" class="entry"> Grant permission if you are logged in to Adobe Analytics (Legacy Login) </th> 
   <th colname="col4" class="entry"> Grant permission if you are logged in to Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server Call Usage </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Log in to Analytics via sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navigate to <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> All admin </span>  &gt; <span class="uicontrol"> User management </span>  &gt; <span class="uicontrol"> Groups </span>  &gt; <span class="uicontrol"> Edit All Report Access </span>  &gt; <span class="uicontrol"> Analytics Tools </span>  &gt; <span class="uicontrol"> Customize </span>  &gt; <span class="uicontrol"> Server Call Usage </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Log in to login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Click <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navigate to <span class="ignoretag"> <span class="uicontrol"> Products </span>  &gt; <span class="uicontrol"> Product Profile </span>  &gt; <span class="uicontrol"> Permissions </span>  &gt; <span class="uicontrol"> Analytics Tools </span>  &gt; <span class="uicontrol"> Server Call Usage </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
