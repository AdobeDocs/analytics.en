---
description: You can customize the delivery schedule for reports. You can stop the delivery at a certain time, or specify the number of times you want to send a report. New schedules use the date range defined in the report. For example, if you create a report for the last 90 days and schedule it to run daily, you receive a report for the last 90 days each day. If you create a report with a static date range from the calendar, you'll see the same report each time it is sent.
seo-description: You can customize the delivery schedule for reports. You can stop the delivery at a certain time, or specify the number of times you want to send a report. New schedules use the date range defined in the report. For example, if you create a report for the last 90 days and schedule it to run daily, you receive a report for the last 90 days each day. If you create a report with a static date range from the calendar, you'll see the same report each time it is sent.
seo-title: Scheduling Manager
solution: Analytics
title: Scheduling Manager
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
index: y
internal: n
snippet: y
---

# Scheduling Manager

You can customize the delivery schedule for reports. You can stop the delivery at a certain time, or specify the number of times you want to send a report. New schedules use the date range defined in the report. For example, if you create a report for the last 90 days and schedule it to run daily, you receive a report for the last 90 days each day. If you create a report with a static date range from the calendar, you'll see the same report each time it is sent.

## Scheduling Manager {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

You can customize the delivery schedule for reports. You can stop the delivery at a certain time, or specify the number of times you want to send a report. New schedules use the date range defined in the report. For example, if you create a report for the last 90 days and schedule it to run daily, you receive a report for the last 90 days each day. If you create a report with a static date range from the calendar, you'll see the same report each time it is sent.

>[!NOTE]
>
>When a user account is disabled, any scheduled report deliveries created by that user are suspended.

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](../../analyze/ad-hoc-analysis/c-tablebuilder.md#concept_664FC77306E148DBA4EA081814943C5E) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis lets you quickly define and schedule reports for specific, timely, ad hoc reporting needs. It is not designed for full exports of data with a massive number or rows, columns, metric evaluations, or extensive breakdowns using data extracts. 
>
>Practical constraints for scheduled reporting in Ad Hoc Analysis are based on this principle: If your report doesn't build within ten minutes (the timeout for Ad Hoc Analysis), then your report is most likely too complex. 
>
>Most likely your report has too many metrics, too many dimension element breakdowns, too many rows or columns, or other extremes that make it too long a report generation process for Ad Hoc Analysis. This type of report needs to be run in Data Warehouse, an Adobe Analytics capability made for full data extraction running offline with report generation that can take many hours or days. 
>
>For example, Ad Hoc Analysis can handle 50,000 rows of data, but breaking down that data for ten browser types means 50,0000 times 10, an exponential increase that may be too complex for an ad hoc reporting tool. Additional breakdowns again increase the rows of data exponentially. Defining the actual number or rows, columns, and breakdowns to constrain for Ad Hoc Analysis reporting cannot be defined in stark terms but is a combination of all these factors.

## Schedule a report for delivery {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Steps that describe how to schedule a report for delivery.

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. On the [!UICONTROL Schedule Manager], click **[!UICONTROL New.]**

## Delivery Options - Definitions {#reference_CA49AC560258471AAE959BCA243F170C}

Definitions for the settings on Delivery Options.

<!-- 

r_delivery_options.xml

 -->

You can send your information as displayed in the currently selected report to the format you select. You can send it one time or set up a delivery schedule, and specify the file format you prefer. You can create and send a digital signature to assure the receiver of the file that it is authentic. You can send the file to an email address or upload it to an FTP server. 

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p> The configurable name of this report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Tells you the report ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> File Format </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Outputs your report in a spreadsheet, including all images. Editable in Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Outputs your report in Comma Separated Values. Editable in a simple text editor (such as Notepad) or a spreadsheet editor (such as Excel). Does not contain any images. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Outputs your report in Portable Document Format. Non-editable and viewable in Adobe Acrobat or Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Outputs your report in a Hypertext Markup Language attachment. This format is what most websites are composed of. Not editable unless you are familiar with HTML code. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Outputs your report in Rich Text Format, including all images. Editable in Microsoft Word or WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Advanced </p> </td> 
   <td colname="col2"> <p> See <a href="../../analyze/ad-hoc-analysis/c-schedule.md#reference_F99B65BF7C9746638D8147EED147015B" type="reference" format="dita" scope="local"> Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Destination </p> </td> 
   <td colname="col2"> <p>Email: Settings to send via email. </p> <p>FTP: Settings for uploading to an FTP server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Range and Delivery Schedule </p> </td> 
   <td colname="col2"> <p>Specifies when to deliver the report. New schedules use the date range defined in the report. For example, if you create a report for the last 90 days and schedule it to run daily, you receive a report for the last 90 days each day. If you create a report with a static date range from the calendar, you'll see the same report each time it is sent. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Advanced Format Settings - Definitions {#reference_F99B65BF7C9746638D8147EED147015B}

Definitions for the settings on Advanced Format Settings.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Field </p> </th> 
   <th colname="col2" class="entry"> <p>Definition </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Filename </p> </td> 
   <td colname="col2"> <p>A user defined file name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Append ID to filename </p> </td> 
   <td colname="col2"> <p>Automatically appends the report ID to the file name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Append date to filename </p> </td> 
   <td colname="col2"> <p> Automatically appends the date of the report to the filename. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Language </p> </td> 
   <td colname="col2"> <p> Lets you select a language for the report. You can send the report in any of the following languages regardless of the language that you use </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">English </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Spanish </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Simplified Chinese </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Traditional Chinese </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">French </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">German </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Japanese </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Portuguese </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Encoding </p> </td> 
   <td colname="col2"> <p>Specifies an encoding type. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Send Report as a Compressed File </p> </td> 
   <td colname="col2"> <p> Compresses the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Send Digital Signature File </p> </td> 
   <td colname="col2"> <p>Creates a digital signature to send with the email. </p> </td> 
  </tr> 
 </tbody> 
</table>

