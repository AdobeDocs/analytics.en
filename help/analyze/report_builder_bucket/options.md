---
description: On the Options panel, you can specify the date settings, latency settings (Current Data), log information, and configure updates.
seo-description: On the Options panel, you can specify the date settings, latency settings (Current Data), log information, and configure updates.
seo-title: Report Builder options
solution: Analytics
title: Report Builder options
topic: Report builder
uuid: 1eef2466-9d27-4793-b5b2-f6155ddc940c
index: y
internal: n
snippet: y
translate: y
---

# Report Builder options

In the Add-Ins toolbar, click **[!UICONTROL  Options]**.  ![](assets/options_icon.png) 

<table id="table_CFBE06044645468F8C883F2370C31F36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colspan="2"> <b> <span class="wintitle"> As Of Date</span> </b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Set to current date</span> </td> 
   <td colname="col2">Lets you specify or reset the <span class="wintitle"> As Of Date</span> so that report builder uses the current date or asks you which date to use upon refresh. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Ask me to set upon refresh</span> </td> 
   <td colname="col2">Lets you set the <span class="wintitle"> As Of Date</span> when refreshing a request. </td> 
  </tr> 
  <tr> 
   <td colspan="2"> <b> <span class="wintitle"> Data Recency</span> </b> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Include Current Data</span> </td> 
   <td colname="col2"> <p>Lets you view data latency (also known as <span class="wintitle"> Data Recency</span>) down to the minute in reporting, occasionally even before this data has been processed by <span class="keyword"> Adobe Analytics</span>. </p> <p>When you do not use this option, <span class="term"> finalized mode</span> (processed) is used, which is typically more <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=data_latency" format="https" scope="external"> latent</a>. </p> <p>This setting applies to all requests in the workbook that are compatible Current Data. If the request is not compatible, the finalized mode is applied. </p> <p>Note the following situations for using the <span class="wintitle"> Include Current Data</span> mode: </p> <p> <b>Format Options</b>: You can specify whether to display this information (Data Recency) when <a href="../report_builder_bucket/layout/t_format_display_headers.md#task_45C7C4938C2C47FCB02634A1248AA831" format="dita" scope="local"> formatting display headers</a>. </p> <p> <b>Breakdowns</b>: Not supported. If the <span class="wintitle"> Data Recency</span> mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. Other requests, however, continue to use Current Data mode. </p> <p> <b>Request Manager</b>: You can view a Current Data column in the Request Manager, so that you can see if the setting is applied to a scheduled request. </p> <p> <b>Scheduled Workbooks</b>: This mode is stored during the scheduling process at the workbook level. If you open a scheduled workbook that is using finalized data, and apply Include Current Data, current mode is used thereafter. </p> <p> <b>Permissions</b>: For users who do not have access to current data, this option is hidden. </p> <p>When enabling this option, if one or more requests cannot be applied, a warning is issued. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Disable Current Data incompatible request warnings </td> 
   <td colname="col2"> <p>Displays warnings if the <span class="wintitle"> Include Current Data</span> mode is selected but the data mode cannot be applied to the edited request. </p> <p>For example, if you set<span class="wintitle"> Include Current Data</span>, and then edit a request that has a segment selected, a warning is issued. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log report builder requests to local file (for troubleshooting) </td> 
   <td colname="col2"> Lets you log requests to a local file. Use this log file for troubleshooting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interpret typed value... </td> 
   <td colname="col2">Interprets a typed value in a filter control as a cell location before considering it a filter expression. <p>For example if you create a Top 10 Page request, using a filter <span class="term"> shoes</span>, the request would display a cell containing something similar to: </p> <p><span class="codeph"> Filter: Top 1-10 Page, Page contains Shoes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update when a new version is available </td> 
   <td colname="col2"> Tells the system to notify you if a new version is available for installation. </td> 
  </tr> 
 </tbody> 
</table>

