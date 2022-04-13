---
description: You can create a new report suite by selecting a pre-defined template, or by using one of your existing report suites to serve as a model.
title: New report suite - settings
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
---
# New report suite - settings

You can create a new report suite by selecting a pre-defined template, or by using one of your existing report suites to serve as a model.

Descriptions of the elements used when [creating a report suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>The [Virtual Report Suite documentation](/help/components/vrs/c-workflow-vrs/vrs-create.md) shows you how to create virtual report suites.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Report Suite ID </span> </td> 
   <td colname="col2"> <p>Specifies a unique ID that can contain only alphanumeric characters. This ID cannot be changed after it is created. Adobe sets the required ID prefix and it cannot be changed, either. </p> <p>When creating multiple report suites, ensure that the naming convention you use guarantees unique report suite IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Site Title</span> </td> 
   <td colname="col2">Identifies the report suite in <span class="wintitle"> Admin Tools</span>. This title is also used in the <span class="wintitle"> Report Suite</span> drop-down list in the suite header. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Time Zone</span> </td> 
   <td colname="col2"> Schedules events and time stamp data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base URL</span> </td> 
   <td colname="col2"> (Optional) Defines the base domain for the report suite. This URL functions as an internal URL filter if you do not explicitly define internal URL filters for the report suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Default Page</span> </td> 
   <td colname="col2"> <p>(Optional) Strips occurrences of the <span class="wintitle"> Default Page</span> value from URLs it encounters. If your <span class="wintitle"> Most Popular Pages</span> report contains URLs rather than page names, this setting prevents multiple URLs for the same web page. </p> <p>For example, the URLs<span class="filepath"> https://example.com</span> and <span class="filepath"> https://example.com/index.html</span> are typically the same page. You can remove extraneous filenames so that both these URLs show up as <span class="filepath"> https://example.com</span> in your reports. </p> <p>If you do not set this value, Analytics automatically removes the following filenames from URLs: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span>, and<span class="filepath"> home.asp</span>. </p> <p>To disable filename stripping, specify a Default Page value that never occurs in your URLs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Go Live Date </p> </td> 
   <td colname="col2">Informs Adobe of the date that you expect this report suite to become active. If your deployment schedule changes, provide an updated traffic estimate using the <span class="wintitle"> Permanent Expected Traffic</span> tool in <a href="/help/admin/c-traffic-management/traffic-management.md"> Traffic Management</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Estimated Page Views Per Day</span> </td> 
   <td colname="col2"> Identifies the estimated number of page views you expect this report suite to support in a day. Large traffic volumes require a longer approval process. To avoid processing delays, be as accurate as possible with this estimate. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Base Currency</span> </td> 
   <td colname="col2"> <p>Specifies the default currency used to store all monetary data. Analytics reporting converts transactions in other currencies to the base currency, using the current conversion rate at the time it receives the data. </p> <p> Analytics reporting uses the <span class="varname"> currencyCode</span> JavaScript variable to identify the currency of a given transaction. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Disable Multi-byte Character Support </span> </td> 
   <td colname="col2"> <p>Disables multibyte character support for the report suite. If you disable multibyte character support, the system assumes that data is in ISO-8859-1 format. Web pages must specify their character set in the <span class="varname"> charSet</span> JavaScript variable. </p> <p>Multibyte character support stores characters in the report suite using UTF-8. Upon receipt, the system converts data from your web page's character set to the UTF-8 character set, so you can use any language in your marketing reports. </p> <p>Contact your Account Manager or Customer Care to change the multibyte character support for an existing report suite. </p> </td> 
  </tr>  
 </tbody> 
</table>
