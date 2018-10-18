---
description: Frequently asked questions for setting up, configuring, and employing features in Activity Map.
seo-description: Frequently asked questions for setting up, configuring, and employing features in Activity Map.
seo-title: Activity Map FAQ
solution: Analytics
title: Activity Map FAQ
topic: Activity map
uuid: dfa9f590-319b-4aef-a135-cd15c716e62f
index: y
internal: n
snippet: y
---

# Activity Map FAQ

Frequently asked questions for setting up, configuring, and employing features in Activity Map.

 [1. Implementation and AppMeasurement](c_Activity Map_FAQ.md#section_FB46DD652E854C07AD339D7DD5CBCEC6)

[2. Activity Map Application](c_Activity Map_FAQ.md#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D)

[3. Segmentation in Activity Map](c_Activity Map_FAQ.md#section_44D6C5F59B8542DC8A3AF38BD8078DCA)

[4. Virtual Report Suites](../activity_map/activitymap-faq.md#section_BDB0CA9E732F478EAC349A79753A78DB)

## 1. Implementation and AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

|  **Q: What are the implementation steps for enabling the new Activity Map?** |A: Please review [Enabling Activity Map](activitymap-enable.md#concept_4C5A1178C8E040B99CAE7A25473E67D6)  |
|---|---|
|  **Q: Do all Analytics customers have access to the Admin Tools ActivityMap Enablement page?** | A: Adobe SiteCatalyst customers do not have access to the Admin Console’s Activity Map Enablement page. Only companies under Adobe Analytics Standard and Adobe Analytics Premium contract have access to this configuration page.  |
|  **Q: Can the new AppMeasurement code be configured through Dynamic Tag Management (DTM)?** |A: Yes, you can [manually implement](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) the new AppMeasurement code.  |
|  **Q: What are the big changes in the AppMeasurement v1.6 library?** | A: The only change in AppMeasurement v1.6 is in the Activity Map link tracking process methodology that requires the collection of Page name, Link ID and RegionID.  |
|  **Q: Will AppMeasurement be rolled out at the domain level rather than on specific pages?** | A: AppMeasurement is rolled out at the report-suite level. The report-suite level is typically associated with a domain level, but this differs with each implementation.  |
|  **Q: DTM automatically loads an older version (1.3.4) of the Visitor API than Activity Map wants (1.5.1). Is this a problem?** | A: No. Activity Map functionality is not dependent on the VisitorAPI.  |

## 2. Activity Map application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

<table id="table_7EFBE9CC801A4D2FB183407D177193B3"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q: Can I use Activity Map if I did not previously use Visitor ClickMap on my website?</b> </td> 
   <td colname="col2"> A: Having the legacy version - now simply called ClickMap - installed is not a prerequisite for implementing the new version. Adobe will continue to support the legacy version for a limited period of time. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: What browsers and versions are supported by Activity Map?</b> </td> 
   <td colname="col2"> A: We support only the latest version of the four main browsers (Chrome, Firefox, Safari and IE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: What are the default Overlay Settings?</b> </td> 
   <td colname="col2">A: By default, Activity Map shows ALL links that have collected data. <p>When popup panels are shown on top of customer web pages, overlays belonging to links that are located below the popup panel may be shown on top of the popup panel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Why are some ranked item overlays missing?</b> </td> 
   <td colname="col2"> A: Some ranked links may be hidden from the page (submenu links, for example). As a consequence, their corresponding link overlays will not be shown. So you can expect to see overlay rankings that are missing some specific rank values, because the rank is computed to for all links in the page (the present one + the hidden ones). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: How is link ranking determined in the All Links report?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_B77406AACCF64414BF659EC5E067123D"> 
     <li id="li_1A3A2FC4CFC9412DAE9CF73383D30F6B">In <b>Gradient</b> and <b>Bubble</b> mode: Ranking is determined by the metric column. For links with same metric value, the rank is further based on link ID alphabetical order. </li> 
     <li id="li_12F38072BDF84DD58280DA5FC6EA44C1">In <b>Gainer &amp; Loser</b> mode, rank is primarily determined by the % Gain column. For links with the same Gain, the rank is further based on the link ID alphabetical order. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Why is link click data not collected when Activity Map is running?</b> </td> 
   <td colname="col2"> A: While Activity Map is in use, link click data is not collected by the Analytics tag. This behavior follows the behavior of the ClickMap plugin. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Why does the metric drop-down list the same metric multiple times?</b> </td> 
   <td colname="col2"> <p>A: Activity Map lists metrics for all report suites. As a result, you can expect to see duplication if the company has not gone through a <a href="https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html" format="https" scope="external"> metric consolidation process</a>. </p> <p>The Metric drop-down lets you limit the list of calculated metrics to the ones assigned to the visited page's report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: How does the Activity Map All Links Report compare with Reports &amp; Analytics Activity Map reporting?</b> </td> 
   <td colname="col2">A: To pull the All Links Report in Activity Map, we create a breakdown request as follow: Activity Map Page = “visitedpage”, broken down by Activity Map Link&amp;Region in <span class="codeph"> &lt;list of link&amp;regions present in the page at rendering time&gt;</span>. <p>To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the Activity Map Page report. There, you would filter for the visited pagename in Activity Map. The visited Pagename is shown in the left column in the Activity Map Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose Activity Map Links &amp; Regions as a secondary dimension. </p> <p>However, it is important to note that the obtained report in R&amp;A will list all Links &amp; Regions that were collected for that Page. But Activity Map only reports on Links&amp;Regions that are currently present in the webpage. So if you have a news site, it will only show data for the news story present at this time, and not the news stories that were present earlier in the day. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: How does Activity Map work with pages containing multiple tags listing multiple report suites?</b> </td> 
   <td colname="col2"> <p>A: By default, Activity Map uses the report suite that is associated with the first tag that is sent by the page. </p> <p>You can select a different tagged report suite through the <span class="ignoretag"><span class="uicontrol"> Activity Map Settings</span> &gt; <span class="uicontrol"> Others</span></span> tab. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: For how long does Activity Map scan for the Analytics Tag?</b> </td> 
   <td colname="col2"> A: We scan for the Analytics tag for up to 20 seconds after a page complete event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: How does Activity Map handle dynamic content?</b> </td> 
   <td colname="col2">A: Activity Map checks every 2 seconds to see if it has found changes in the state of the web page such as: 
    <ul id="ul_AF929C89E2FD41989DD924B7931C423F"> 
     <li id="li_A810C13AAD79499B97CF61CAD8AFA68F">HTML content that has become visible </li> 
     <li id="li_4093B87F8A7F4559AFD98DAE835A5484">HTML content that is hidden </li> 
     <li id="li_EB584F7FEC7D44B1AF493E7DA026A378">New HTML content that was injected </li> 
    </ul>If content is hidden or shown, the application automatically changes the affected links state (and therefore overlays) from hidden to shown or from shown to hidden. <p>If new content is injected, the application will retrieve the associated links, pull analytics data for them, and add overlays for these links. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: What metric is the Page Flow report based on?</b> </td> 
   <td colname="col2"> A: All data shown is based on page views. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Can you explain Activity Map behavior with various type of pages?</b> </td> 
   <td colname="col2"> <b>Web page without Analytics tag</b> 
    <ul id="ul_10396922D2484C7CA269E7A3E5457F89"> 
     <li id="li_3955512D61D040DAA5FE55169C304BD1">A warning message is shown below toolbar indicating that no tag is present. </li> 
    </ul> <p> <b>Web page with incompatible Analytics Tag (AppMeasurement v1.5 or earlier)</b> </p> 
    <ul id="ul_85780A2E509641599E5DCADAB2096428"> 
     <li id="li_B2FEAD8AE1474EDEB0891EB1B01AEEF8">A warning message is shown indicating that you need to <a href="activitymap-enable.md#section_5D1586289DF2489289B1B6C1C80C300D" format="dita" scope="local"> upgrade the page code to v1.6</a>. </li> 
    </ul> <p> <b>Web page with compatible Analytics Tag (AppMeasurement v1.6 or later), but Activity Map reporting was not enabled in Admin Tools</b> </p> 
    <ul id="ul_F16BFD92CE1B4391ABFDE27E454033CE"> 
     <li id="li_8ABF0A222EFF406CB53B40DA5A8C06CB">A warning message is shown indicating that you need to ask your Admin to <a href="activitymap-enable.md#section_D14F15D2FC0346FCAD8B3B87E6DD33D4" format="dita" scope="local"> enable the Activity Map report</a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Can I export Activity Map data (contextData) via <a href="https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html" format="html" scope="external"> Analytics Data Feed</a> ?</b> </p> </td> 
   <td colname="col2"> <p>A: No. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 3. Segmentation in Activity Map {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

|  **Q: Are segments tied to the individual user segments? Or are shared Admin-level segments available in Activity Map?** | A: Activity Map inherits your Admin-level segments (reporting segments) from Reports & Analytics.  |
|---|---|
|  **Q: Do segments work in Live mode?** | A: No, segments do not work in Live mode. The functionality is equivalent to that of real-time reporting in Reports & Analytics.  |

## 4. Virtual report suites {#section_BDB0CA9E732F478EAC349A79753A78DB}

|  **Q: Is Activity Map compatible with virtual report suites?** | A: Yes. However, due to virtual report suite limitations, Activity Map's Live Mode is not compatible with virtual report suites.  |
|---|---|

