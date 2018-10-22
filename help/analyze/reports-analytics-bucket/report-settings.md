---
description: Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.
seo-description: Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.
seo-title: Report display settings and navigation
solution: Analytics
title: Report display settings and navigation
topic: Reports,Reports and analytics
uuid: db8fe877-7671-420c-a9ec-cb9e81a515a3
index: y
internal: n
snippet: y
---

# Report display settings and navigation

Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu.

## Report display settings and navigation {#concept_09832A2CA0FF4982B1AA37C1B635220B}

Settings that define how all reports appear and information that aps the default menu options to their location in the simplified menu. 

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Report Settings]** 

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

## Navigation Menu {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

If you are used to the default menu, the following table makes it easier for you to find the menu options in the simplified menu.  

|  Location in Default Menu  | Location in Simplified Menu  |
|---|---|
|  **Site Metrics** |  |  |
|   | Site Overview  | Metrics > Site Overview  |
|   | Key Metrics  | Metrics > Key Metrics  |
|   | Page Views  | Metrics > Page Views  |
|   | Visits  | Metrics > Visits  |
|   | Visitors  | Metrics > Visitors  |
|   | Time Spent per Visit  | Metrics > Time Spent per Visit  |
|   | Time Prior to Event  | Conversion > Time Prior to Event  |
|   | Purchases  | Metrics > Purchases  |
|   | Shopping Cart  | Metrics > Shopping Cart  |
|   | Custom Events  | Metrics > Custom Events  |
|   | Bots  | Audience > Bots  |
|   | Anomaly Detection  | Metrics > Anomaly Detection  |
|   | Real-Time  | Metrics > Real-Time  |
|  **Site Content** |  |  |
|   | Pages  | Content > Pages  |
|   | Site Sections  | Content > Site Sections  |
|   | Servers  | Content > Servers  |
|   | Links  | Navigation > Custom Links; Navigation > Exit Links; Navigation > ClickMap; Navigation > File Downloads  |
|   | Pages Not Found  | Navigation > Pages Not Found  |
|  **Mobile** |  |  |
|   | Devices  | Audience > Mobile > Devices  |
|   | Device Type  | Audience > Mobile > Device Type  |
|   | Manufacturer  | Audience > Mobile > Manufacturer  |
|   | Screen Size  | Audience > Mobile > Screen Size  |
|   | Screen Height  | Audience > Mobile > Screen Height  |
|   | Screen Width  | Audience > Mobile > Screen Width  |
|   | Cookie Support  | Audience > Mobile > Cookie Support  |
|   | Image Support  | Audience > Mobile > Image Support  |
|   | Color Depth  | Audience > Mobile > Color Depth  |
|   | Audio Support  | Audience > Mobile > Audio Support  |
|   | Video Support  | Audience > Mobile > Video Support  |
|   | Operating System  | Audience > Mobile > Operating System  |
|  **Paths** |  |  |
|   | Pages  | Navigation > Paths > Pages  |
|   | Internal Search Terms  | Navigation > Paths > Internal Search Terms  |
|  **Traffic Sources** |  |  |
|   | Search Keyword - All  | Traffic Sources > Search Keyword - All  |
|   | Search Keyword - Paid  | Traffic Sources > Search Keyword - Paid  |
|   | Search Keyword - Natural  | Traffic Sources > Search Keyword - Natural  |
|   | Search Engines - All  | Traffic Sources > Search Engines - All  |
|   | Search Engines - Paid  | Traffic Sources > Search Engines - Paid  |
|   | Search Engines - Natural  | Traffic Sources > Search Engines - Natural  |
|   | All Search Page Ranking  | Traffic Sources > All Search Page Ranking  |
|   | Referring Domains  | Traffic Sources > Referring Domains  |
|   | Original Referring Domains  | Traffic Sources > Original Referring Domains  |
|   | Referrers  | Traffic Sources > Referrers  |
|   | Referrer Types  | Traffic Sources > Referrer Types  |
|  **Campaigns** |  |  |
|   | Campaign Conversion Funnel  | Traffic Sources > Campaigns > Campaign Conversion Funnel  |
|   | Tracking Code  | Traffic Sources > Campaigns > Tracking Code  |
|  **Products** |  |  |
|   | Products Conversion Funnel  | Conversion > Products > Products Conversion Funnel  |
|   | Products  | Conversion > Products > Products  |
|   | Cross Sell  | Conversion > Products > Cross Sell  |
|   | Categories  | Conversion > Products > Categories  |
|  **Visitor Retention** |  |  |
|   | Return Frequency  | Audience > Visitor Retention > Return Frequency  |
|   | Return Visits  | Audience > Visitor Retention > Return Visits  |
|   | Daily Return Visits  | Audience > Visitor Retention > Daily Return Visits  |
|   | Visit Number  | Audience > Visitor Retention > Visit Number  |
|   | Sales Cycle  | Audience > Visitor Retention > Sales Cycle  |
|  **Visitor Profile** |  |  |
|   | GeoSegmentation  | Audience > Visitor Profile > GeoSegmentation  |
|   | Languages  | Audience > Visitor Profile > Languages  |
|   | Time Zones  | Audience > Visitor Profile > Time Zones  |
|   | Domains  | Audience > Visitor Profile > Domains  |
|   | Top Level Domains  | Audience > Visitor Profile > Top Level Domains  |
|   | Technology  | Audience > Visitor Profile > Technology  |
|   | Visitor State  | Audience > Visitor Profile > Visitor State  |
|   | Visitor ZIP/Postal Code  | Audience > Visitor Profile > Visitor ZIP/Postal Code  |
|  **Custom Conversion** |  |  |
|   | Custom Conversion 1-10  | Conversion > Custom Conversion > Custom Conversion 1-10  |
|   | Custom Conversion 11-20  | Conversion > Custom Conversion > Custom Conversion 11-20  |
|  **Custom Traffic ** |  |  |
|   | Custom Traffic 1-10  | Content > Custom Traffic > Custom Traffic 1-10  |
|  **Test&Target ** |  | Conversion > Test&Target  |
|  **Survey** |  | Audience > Survey  |
|  **Marketing Channels** |  |  |
|   | Channel Overview Report  | Traffic Sources > Marketing Channels > Channel Overview Report  |
|   | First Touch Channel  | Traffic Sources > Marketing Channels > First Touch Channel  |
|   | First Touch Channel Detail  | Traffic Sources > Marketing Channels > First Touch Channel Detail  |
|   | Last Touch Channel  | Traffic Sources > Marketing Channels > Last Touch Channel  |
|   | Last Touch Channel Detail  | Traffic Sources > Marketing Channels > Last Touch Channel Detail  |
|  **Mobile App** |  |  |
|   | Mobile App Overview  | Content > Mobile App > Mobile App Overview  |
|   | Lifecycle Reports  | Content > Mobile App > Lifecycle Reports  |
|  **Custom Reports ** |  |  |
|   | Custom reports show up only of you have any set up.  | Custom Reports  |
|   |  |  |

