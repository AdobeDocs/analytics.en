---
description: The Billing page lets you access billing information, including traffic details for each report suite. Only an authorized administrator has access to this page.
seo-description: The Billing page lets you access billing information, including traffic details for each report suite. Only an authorized administrator has access to this page.
seo-title: Billing
solution: Analytics
title: Billing
topic: Admin tools
uuid: 76122fcc-7f18-446d-9336-a08886f91ef3
index: y
internal: n
snippet: y
---

# Billing

The Billing page lets you access billing information, including traffic details for each report suite. Only an authorized administrator has access to this page.

>[!NOTE]
>
>If access to the billing tab is disabled for your company, contact your Account Manager.

The traffic overview data from the billing page lets you correlate page view data in reports with billable server calls on your invoice. The [!UICONTROL Billing] page lets you do the following:

* Audit your invoice. 
* Break down costs by report suite for internal accounting allocations. 
* View the distribution of primary and secondary server calls.

The [!UICONTROL Billing] page organizes information by month.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

The resulting [!UICONTROL Monthly Invoice] report includes the following information: 

<table id="table_526AB4C5DEAB48369C6F64BF7EA3EA1A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Report Suite </span> </p> </td> 
   <td colname="col2"> <p>The report suite involved in the data collection activity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Location</span> </p> </td> 
   <td colname="col2"> <p>The data center that stores the report suite data: San Jose (California), Dallas (Texas), Pacific Northwest (US), London (UK), or Singapore. In most cases, all company report suites are located in the same data center. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Primary Server Calls </span> </p> </td> 
   <td colname="col2"> <p>Requests received directly from website visitor browsers or the Data Insertion API. Includes Primary Hits (Page Views), Primary Custom Events, Primary Download Events, and Primary Exit Events. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Secondary Server Calls </span> </p> </td> 
   <td colname="col2"> <p>Copies of primary server calls created by multi-suite tags or copied/moved by a VISTA rule. </p> <p>If a secondary server call has been moved (not copied) to a different report suite by a VISTA rule, the <span class="wintitle"> Billing</span> page identifies this transfer with a negative number. In this case, the accumulated secondary calls are deducted from the primary server calls. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Total Server Calls </span> </p> </td> 
   <td colname="col2"> <p>The combined total of primary and secondary server calls for this report suite at the given location. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Page Views </span> </p> </td> 
   <td colname="col2"> <p>Page view totals for each report suite. You can confirm page view values in <span class="uicontrol"></span> <span class="uicontrol"> Site Metrics</span> &gt; <span class="uicontrol"> Page Views</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Downloads </span> </p> </td> 
   <td colname="col2"> <p>Download totals for each report suite. You can confirm the download values in <span class="uicontrol"> Site Content</span> &gt; <span class="uicontrol"> Links</span> &gt; <span class="uicontrol"> File Downloads</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Custom Links </span> </p> </td> 
   <td colname="col2"> <p>Custom link totals for each report suite. You can confirm the custom link values in <span class="uicontrol"> Site Content</span> &gt; <span class="uicontrol"> Links</span> &gt; <span class="uicontrol"> Custom Links</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Exit Links </span> </p> </td> 
   <td colname="col2"> <p>Exit link totals for each report suite. You can confirm the exit link values in <span class="uicontrol"> Site Content</span> &gt; <span class="uicontrol"> Links</span> &gt; <span class="uicontrol"> Exit Links</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>To obtain a working copy of the [!UICONTROL Monthly Invoice] report, copy it onto your clipboard, then paste it into a spreadsheet program such as Microsoft Excel&#42;.

## Reporting Date vs. Processing Date {#section_51A48C2F223F4904BE1407C13333C457}

In the reporting user interface, the data presented is always attached to the **Reporting Date**, which is the timestamp that is attached to the event.

Usage/Billing, on the other hand, always uses the **Processing Date**, or when the data was actually processed in the system. Due to basic latency, data imports, or event time zone differences (everything is processed in Pacific Time) the Reporting Date and Processing Date do not typically match up completely. 
