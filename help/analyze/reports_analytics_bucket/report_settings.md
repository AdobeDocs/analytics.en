---
description: Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.
seo-description: Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.
seo-title: Report Display Settings and Navigation
solution: Analytics
title: Report Display Settings and Navigation
topic: Reports,Reports and analytics
uuid: 6ca2f49c-1a74-48c4-b38d-2d5f2d0eb944
index: y
internal: n
snippet: y
translate: y
---

# Report Display Settings and Navigation

## Report Display Settings and Navigation {#concept_09832A2CA0FF4982B1AA37C1B635220B}
>Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.** [!UICONTROL  Analytics] ** > ** [!UICONTROL  Components] ** > ** [!UICONTROL  Report Settings] ** 

<table id="table_4D50536CF58B422683DAB5A17750E7D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colspan="2"> <b>General Settings</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include related metrics section </p> </td> 
   <td colname="col2"> <p>Related metrics are closely related to the report you are currently viewing (for example, the top five pages in the page views report). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show internet average in details section </p> </td> 
   <td colname="col2"> <p>Expresses the average value for a given statistic, taken across several thousand business websites. When enabled, this section appears as a separate column in the report summary and report details sections. This feature is used only by the traffic reports in the technology group, as well as the search engines, languages, and domains reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show Adobe's default menu structure </p> </td> 
   <td colname="col2"> <p>Ignores the settings in the Admin Tools, where administrators customize report menus to fit user preferences, returning the report menu to default settings. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Force column widths when displaying reports </p> </td> 
   <td colname="col2"> <p>Forces report column widths to an aesthetically pleasing consistency. This setting is useful when more than three metrics are displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <b>Graphs and Charts</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Highlight weekends on trending graphs </p> </td> 
   <td colname="col2"> <p>Vertically highlights the weekend dates of trended report graphs. Trended reports can be much easier to evaluate when the weekends are identified. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include forecast in graph and summary </p> </td> 
   <td colname="col2"> <p>Estimates how much a particular statistic will occur in the future. The forecast appears in the report summary section when enabled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include Calendar Events in Reports </p> </td> 
   <td colname="col2"> <p>Tracks site performance relative to specific events. When enabled, these events appear on your reports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Flash graphs </p> </td> 
   <td colname="col2"> <p>Enables Flash graphs in your reports. Flash graphs provide sharper, more interactive images for reports, but do not allow you to easily copy or save the images. For quick image copying or saving functionality, disable this option (images will be in <span class="filepath"> .gif </span> format). If you deselect this option, the copy graph button does not appear in the report toolbar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show "All Others" data in selected graphs </p> </td> 
   <td colname="col2"> <p>Displays all others below the top five grouped in a single object. (Bar charts show the top five web pages or other data within your report.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show "None", "Unspecified" and "Typed/Bookmarked" data in report graphs </p> </td> 
   <td colname="col2"> <p>Shows metrics where no value received credit for the metric specified. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Show sparklines on ranked reports </p> </td> 
   <td colname="col2"> <p>Displays a sparkline in the totals field of ranked reports. This provides a quick view of the overall trend without generating a separate report. </p> </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <b>Acceleration</b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable Report Accelerator to view reports more quickly </p> </td> 
   <td colname="col2"> <p> Enables the report accelerator, which uses a time- based algorithm to cache recently requested reports and examines only the most frequently occurring unique items, resulting in even faster delivery of reports. By caching requested reports for 15 minutes, the report accelerator can retrieve those reports for subsequent requests almost instantaneously. This setting is helpful when browsing back and forth, printing reports, or for frequent access to the same reports. When disabled, the system regenerates reports each time they are requested. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable Dashboard Accelerator and display available cached versions </p> </td> 
   <td colname="col2"> <p>Enables the dashboard accelerator, which stores a cached version of your dashboard for subsequent viewing. By caching a view of your dashboard for 24 hours, the dashboard accelerator is able to retrieve that view almost instantaneously because the intensive database querying and processing is done ahead of time. If the available cached version is more than 24 hours old, a new dashboard is generated and a new, cached version created. Likewise, a new, cached version is created whenever you update the dashboard (or any reportlet displayed on the dashboard). The cache is user-based. Other users viewing a shared dashboard see a version based on their own use of dashboard accelerator and updating of the dashboard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable network acceleration for improved report performance </p> </td> 
   <td colname="col2"> <p>Speeds delivery of the data to your location by optimizing the path between the Adobe infrastructure and your environment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Language/Currency/Encoding </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Thousands Separator </span>: Select a separator for every <span class="term"> thousands </span> (decimal or comma). Many countries use a decimal to separate the thousands number. (This separator is applied to all numbers throughout the system, not just currency.) </p> <p> <span class="uicontrol"> Use the report suite's default currency </span>: Specifies whether to use the report suite's default currency. </p> <p> <span class="uicontrol"> Currency </span>: The currency to which you want to convert your data. When a value is selected in this setting, the data stored in the database is not affected, but is shown as a converted value based on the current day's currency conversion rate. When currency options are not configured (set to the defaults) no currency conversion takes place, and all values are stored and displayed in U.S. dollars (USD). To convert the currency when the data is processed (before it is displayed), contact your account manager. </p> <p> <span class="uicontrol"> Scheduled Report Encoding </span>: SHIFT-JIS for Japanese character encoding. EUC-JP for extended Unix Code, primarily for Japanese, Korean, and simplified Chinese. </p> <p> <span class="uicontrol"> CSV Separator Character </span>: The character you want to use to separate CSV values. </p> </td> 
  </tr> 
 </tbody> 
</table>

>## Navigation Menu {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- nav_menu.xml -->
If you are used to the default menu, the following table makes it easier for you to find the menu options in the simplified menu. 

|  Location in Default Menu  | Location in Simplified Menu  |
|---|---|
|  **Site Metrics** |  |  |
|   | Site Overview  | Metrics &amp;gt; Site Overview  |
|   | Key Metrics  | Metrics &amp;gt; Key Metrics  |
|   | Page Views  | Metrics &amp;gt; Page Views  |
|   | Visits  | Metrics &amp;gt; Visits  |
|   | Visitors  | Metrics &amp;gt; Visitors  |
|   | Time Spent per Visit  | Metrics &amp;gt; Time Spent per Visit  |
|   | Time Prior to Event  | Conversion &amp;gt; Time Prior to Event  |
|   | Purchases  | Metrics &amp;gt; Purchases  |
|   | Shopping Cart  | Metrics &amp;gt; Shopping Cart  |
|   | Custom Events  | Metrics &amp;gt; Custom Events  |
|   | Bots  | Audience &amp;gt; Bots  |
|   | Anomaly Detection  | Metrics &amp;gt; Anomaly Detection  |
|   | Real-Time  | Metrics &amp;gt; Real-Time  |
|  **Site Content** |  |  |
|   | Pages  | Content &amp;gt; Pages  |
|   | Site Sections  | Content &amp;gt; Site Sections  |
|   | Servers  | Content &amp;gt; Servers  |
|   | Links  | Navigation &amp;gt; Custom Links; Navigation &amp;gt; Exit Links; Navigation &amp;gt; ClickMap; Navigation &amp;gt; File Downloads  |
|   | Pages Not Found  | Navigation &amp;gt; Pages Not Found  |
|  **Mobile** |  |  |
|   | Devices  | Audience &amp;gt; Mobile &amp;gt; Devices  |
|   | Device Type  | Audience &amp;gt; Mobile &amp;gt; Device Type  |
|   | Manufacturer  | Audience &amp;gt; Mobile &amp;gt; Manufacturer  |
|   | Screen Size  | Audience &amp;gt; Mobile &amp;gt; Screen Size  |
|   | Screen Height  | Audience &amp;gt; Mobile &amp;gt; Screen Height  |
|   | Screen Width  | Audience &amp;gt; Mobile &amp;gt; Screen Width  |
|   | Cookie Support  | Audience &amp;gt; Mobile &amp;gt; Cookie Support  |
|   | Image Support  | Audience &amp;gt; Mobile &amp;gt; Image Support  |
|   | Color Depth  | Audience &amp;gt; Mobile &amp;gt; Color Depth  |
|   | Audio Support  | Audience &amp;gt; Mobile &amp;gt; Audio Support  |
|   | Video Support  | Audience &amp;gt; Mobile &amp;gt; Video Support  |
|   | Operating System  | Audience &amp;gt; Mobile &amp;gt; Operating System  |
|  **Paths** |  |  |
|   | Pages  | Navigation &amp;gt; Paths &amp;gt; Pages  |
|   | Internal Search Terms  | Navigation &amp;gt; Paths &amp;gt; Internal Search Terms  |
|  **Traffic Sources** |  |  |
|   | Search Keyword - All  | Traffic Sources &amp;gt; Search Keyword - All  |
|   | Search Keyword - Paid  | Traffic Sources &amp;gt; Search Keyword - Paid  |
|   | Search Keyword - Natural  | Traffic Sources &amp;gt; Search Keyword - Natural  |
|   | Search Engines - All  | Traffic Sources &amp;gt; Search Engines - All  |
|   | Search Engines - Paid  | Traffic Sources &amp;gt; Search Engines - Paid  |
|   | Search Engines - Natural  | Traffic Sources &amp;gt; Search Engines - Natural  |
|   | All Search Page Ranking  | Traffic Sources &amp;gt; All Search Page Ranking  |
|   | Referring Domains  | Traffic Sources &amp;gt; Referring Domains  |
|   | Original Referring Domains  | Traffic Sources &amp;gt; Original Referring Domains  |
|   | Referrers  | Traffic Sources &amp;gt; Referrers  |
|   | Referrer Types  | Traffic Sources &amp;gt; Referrer Types  |
|  **Campaigns** |  |  |
|   | Campaign Conversion Funnel  | Traffic Sources &amp;gt; Campaigns &amp;gt; Campaign Conversion Funnel  |
|   | Tracking Code  | Traffic Sources &amp;gt; Campaigns &amp;gt; Tracking Code  |
|  **Products** |  |  |
|   | Products Conversion Funnel  | Conversion &amp;gt; Products &amp;gt; Products Conversion Funnel  |
|   | Products  | Conversion &amp;gt; Products &amp;gt; Products  |
|   | Cross Sell  | Conversion &amp;gt; Products &amp;gt; Cross Sell  |
|   | Categories  | Conversion &amp;gt; Products &amp;gt; Categories  |
|  **Visitor Retention** |  |  |
|   | Return Frequency  | Audience &amp;gt; Visitor Retention &amp;gt; Return Frequency  |
|   | Return Visits  | Audience &amp;gt; Visitor Retention &amp;gt; Return Visits  |
|   | Daily Return Visits  | Audience &amp;gt; Visitor Retention &amp;gt; Daily Return Visits  |
|   | Visit Number  | Audience &amp;gt; Visitor Retention &amp;gt; Visit Number  |
|   | Sales Cycle  | Audience &amp;gt; Visitor Retention &amp;gt; Sales Cycle  |
|  **Visitor Profile** |  |  |
|   | GeoSegmentation  | Audience &amp;gt; Visitor Profile &amp;gt; GeoSegmentation  |
|   | Languages  | Audience &amp;gt; Visitor Profile &amp;gt; Languages  |
|   | Time Zones  | Audience &amp;gt; Visitor Profile &amp;gt; Time Zones  |
|   | Domains  | Audience &amp;gt; Visitor Profile &amp;gt; Domains  |
|   | Top Level Domains  | Audience &amp;gt; Visitor Profile &amp;gt; Top Level Domains  |
|   | Technology  | Audience &amp;gt; Visitor Profile &amp;gt; Technology  |
|   | Visitor State  | Audience &amp;gt; Visitor Profile &amp;gt; Visitor State  |
|   | Visitor ZIP/Postal Code  | Audience &amp;gt; Visitor Profile &amp;gt; Visitor ZIP/Postal Code  |
|  **Custom Conversion** |  |  |
|   | Custom Conversion 1-10  | Conversion &amp;gt; Custom Conversion &amp;gt; Custom Conversion 1-10  |
|   | Custom Conversion 11-20  | Conversion &amp;gt; Custom Conversion &amp;gt; Custom Conversion 11-20  |
|  **Custom Traffic ** |  |  |
|   | Custom Traffic 1-10  | Content &amp;gt; Custom Traffic &amp;gt; Custom Traffic 1-10  |
|  **Test&amp;amp;Target ** |  | Conversion &amp;gt; Test&amp;amp;Target  |
|  **Survey** |  | Audience &amp;gt; Survey  |
|  **Marketing Channels** |  |  |
|   | Channel Overview Report  | Traffic Sources &amp;gt; Marketing Channels &amp;gt; Channel Overview Report  |
|   | First Touch Channel  | Traffic Sources &amp;gt; Marketing Channels &amp;gt; First Touch Channel  |
|   | First Touch Channel Detail  | Traffic Sources &amp;gt; Marketing Channels &amp;gt; First Touch Channel Detail  |
|   | Last Touch Channel  | Traffic Sources &amp;gt; Marketing Channels &amp;gt; Last Touch Channel  |
|   | Last Touch Channel Detail  | Traffic Sources &amp;gt; Marketing Channels &amp;gt; Last Touch Channel Detail  |
|  **Mobile App** |  |  |
|   | Mobile App Overview  | Content &amp;gt; Mobile App &amp;gt; Mobile App Overview  |
|   | Lifecycle Reports  | Content &amp;gt; Mobile App &amp;gt; Lifecycle Reports  |
|  **Custom Reports ** |  |  |
|   | Custom reports show up only of you have any set up.  | Custom Reports  |
|   |  |  |


