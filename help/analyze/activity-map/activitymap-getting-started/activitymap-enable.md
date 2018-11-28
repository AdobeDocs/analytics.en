---
description: Explains the steps the Analytics Admin needs to complete to enable Activity Map link collection and user download.
seo-description: Explains the steps the Analytics Admin needs to complete to enable Activity Map link collection and user download.
seo-title: Enable Activity Map
solution: Analytics
title: Enable Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
index: y
internal: n
snippet: y
---

# Enable Activity Map{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable Activity Map link collection and user download.

## 1. Update Your AppMeasurement (Javascript) Code to v1.6 (or higher) {#section_5D1586289DF2489289B1B6C1C80C300D}

The Activity Map module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the Activity Map module when instantiated.

Activity Map data cannot be collected unless you update to this version (or higher) of AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   We have included some [sample implementation code](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) to help you visualize the changes that have been made to the code by including the Activity Map module. 

1. Validate the implementation:

    1. When a clickable element is clicked, data will be stored in a cookie named s_sq. 
    1. The Activity Map data can be seen in the query-string on the tracking call. For example:

       ```    
       …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
       ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

<!-- 

Using 
<b>Dynamic Tag Management (DTM)</b>. To do so, enable the code through the DTM repository.

 -->

<!-- 

This is in an email from Priyanka: 
<p>Once the DTM team believes the feature is ready, we will be pushing it to production. So, it will be available at https://dtm.adobe.com </p> 
<p>DTM admin needs to enable this feature (switch it on) explicitly, only for the beta customers. </p> 
<p>Now, that the Activity Map feature is enabled for the beta customer, he can go into the adobe analytics tool within DTM and enable Activity Map as per step 2 in the document (see email from Priyanka) where he needs to check the configuration mode and app measurement library version etc. </p>

 -->

## 2. Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable Activity Map reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites > [select report suite] > Edit Settings > Activity Map]** > **[!UICONTROL Activity Map Reporting]** . 
1. Activity Map collects the link data in Activity Map reports. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   This step adds all the Analytics dimensions that you need to collect data. 

1. After about an hour, check the [Activity Map Page report](cm_reporting_analytics.md#concept_81460823B3EE43DD8152999F0C96DAF3), which shows all the pages where users clicked on a link.

## 3. Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   This will take you to the group management page in the Admin Console. 

1. [Add users to this group](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) and **[!UICONTROL Save Group]**. 

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** . 

   <!-- 

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> > 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. You can then add Non-Admin users to this group. This level of permission combined with the Activity Map Access will provide comprehensive permissions to download and use the tool. 
</note>

 -->

<!-- 

3. Verify That You are Collecting Activity Map Link Data 
<ol id="ol_6AEA6B8B052A4EE0A90438F7EC87D413"> 
 <li id="li_501EFD2AC99B43C2BD2FA5D97CF10280">Check in your browser's Developer section whether you are collecting link data. (This example uses the Firefox UI.) 
  <ol id="ol_88D8C3468E7E43DCA4F36544307F3C55"> 
   <li id="li_C5AAFC27BCDD497988D00913AAD5A00C">Go to one of your web pages that has Analytics tags implemented. </li> 
   <li id="li_F9220FD0004647189A98C3E0D79E1FC8">Navigate to the developer console: <span class="uicontrol"> Open menu </span> > <span class="uicontrol"> Developer </span> > <span class="uicontrol"> Web console </span>. </li> 
   <li id="li_E3B8159197F54844B0B523AEC7E4BB27">Select the Network tab. </li> 
   <li id="li_4A1DBA7465CD4E54BFCBFBBA0C506785">Search on <span class="codeph"> /b/ss </span> to capture the tag requests. </li> 
   <li id="li_587AD51A69074895B6C3927CFBC66CD7">Click a link in your web page. </li> 
   <li id="li_456E9B9760B6414F978A195B8F47D9A3">Click the top link in the dev console: <img placement="break" align="center" href="assets/dev_console.png" width="500px" id="image_12C58DABB4C6410F8C2E1AE75BD683CA" /> </li> 
   <li id="li_4E45292A17D84A11AF1ECE9750FB4D99">To verify that the link parameters are being sent, click the <span class="wintitle"> Params </span> tab and scroll down to find the Activity Map parameters: <img placement="break" align="center" href="assets/cm_params.png" width="250px" id="image_926374535B1A48059D43C14FDB697D78" /> </li> 
   <li id="li_33349274966A48D99C0978CE6E8B1AB1">Verify that they reflect the link you clicked on and the region on the correct page. </li> 
  </ol> </li> 
</ol>

 -->

