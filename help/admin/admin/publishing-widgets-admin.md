---
description: A Publishing Widget is a container that lets you embed marketing reports (bookmarks and dashboards) on a web page. People in your organization who do not have access to marketing reports can view pertinent data.
seo-description: A Publishing Widget is a container that lets you embed marketing reports (bookmarks and dashboards) on a web page. People in your organization who do not have access to marketing reports can view pertinent data.
seo-title: Publishing Widget
solution: Analytics
title: Publishing Widget
topic: Admin tools
uuid: b2c0b739-35b8-4a88-9c8d-54b2324a488f
index: y
internal: n
snippet: y
---

# Publishing Widget

A Publishing Widget is a container that lets you embed marketing reports (bookmarks and dashboards) on a web page. People in your organization who do not have access to marketing reports can view pertinent data.

For example, you could provide a dashboard so company executives can view the number of page visitors, the number of unique page visitors, and so on.

>[!CAUTION]
>
>No authentication is required to view data published through the Publishing Widget. Because of this, you should consider published data to be no more secure than data sent to an email group or list server. Use the widget only in compliance with your organization's security standards, existing contractual requirements, and applicable law. The Publishing Widget provides the ability to restrict, by IP address or domain path, where you can publish data. However, these mechanisms are intended solely to prevent unintended data distribution, and are not an effective way to secure access to data distributed through the Publishing Widget. 
>
>Adobe assumes no responsibility or liability for data exposed through the Publishing Widget.

Because Publishing Widget can potentially drive high traffic volumes, Adobe reserves the right, at its sole discretion, to disable a company's Publishing widgets for improper use or excessive traffic that is causing an impact to overall performance.

**Troubleshooting - Publishing Widget Cache**

The first time any user sees the deployed publishing widget, the widget runs the report. After the report is run, the results are added to a cache and are valid for 1 hour. Any subsequent user who views the publishing widget within the next hour will see the cached version (it will return instantly). After an hour has passed, any subsequent user who views the publishing widget will force it to run the report again, and then these results are cached, and so on. That way, the data is guaranteed to be at most one hour old.

If you see data differences between the Publishing Widget and the reporting interface, you might need to clear the Publishing Widget cache.

1. Click in the Publishing Widget (so that the widget has focus). 
1. Click **[!UICONTROL Save]** on the widget. 
1. Re-run the widget. (Preview mode does not use the widget's cache.)

>[!NOTE]
>
>Publishing Widgets show only the first column of data in a report.

## Publishing Widgets Descriptions {#section_D67478AECCA946B19A3E4C7071EB4871}

<table id="table_3050E38B58714BB9AA2BE73F40EEA835"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> The name for the widget. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> (Optional) Specify a description for the widget. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report </td> 
   <td colname="col2"> <p>From the top Report drop-down list, select a folder or a dashboard. From the bottom Report drop-down list, select a reportlet or bookmark. </p> <p>These reports do not require visitor authentication. When a visitor loads a web page that includes a Publishing Widget, the widget automatically displays the associated report using current reporting data. Changes to a Publishing Widget, such as changing the associated report, automatically updates the report output for all web pages that use that widget, without you having to redeploy the web pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Destination </td> 
   <td colname="col2"> <p>Specify the destination for the widget. </p> <p> Destinations must be in a valid URL format, including the <span class="codeph"> http://</span> or <span class="codeph"> https://</span> prefix. Publishing widget Destinations are inclusive, meaning that the Publishing widget functions on all URLs that include the specified Destination. For example, a Destination of <span class="codeph"> http://www.corp1.com/sales/</span> allows Publishing widgets on all Web pages at or below the sales page on the <span class="codeph"> www.corp1.com</span> Web site. </p> </td> 
  </tr> 
 </tbody> 
</table>

