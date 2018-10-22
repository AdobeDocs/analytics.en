---
description: Web Log data sources let you import standard web server log files.
seo-description: Web Log data sources let you import standard web server log files.
seo-title: Web log
solution: Analytics
subtopic: Data sources
title: Web log
topic: Developer and implementation
uuid: 97af5fcc-691c-4a99-9b95-d1dbc38d62b1
index: y
internal: n
snippet: y
---

# Web log

Web Log data sources let you import standard web server log files.

The following common web server log types are supported: 

<table id="table_50EDC9237759448A8471C42ABC8F79F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column Name </p> </th> 
   <th colname="col2" class="entry"> <p> Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>NCSA Common Log </p> </td> 
   <td colname="col2"> <p>Apache Default </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NCSA Extended (Combined) </p> </td> 
   <td colname="col2"> <p>Apache </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>W3C Extended Log </p> </td> 
   <td colname="col2"> <p>Used by IIS 4.0 and later </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS Log </p> </td> 
   <td colname="col2"> <p> Used by IIS 3.0 and earlier </p> </td> 
  </tr> 
 </tbody> 
</table>

The primary log file fields that Data Sources processes include IP Address, Date/Time of the request, and the URL. In a few cases, such as the NCSA Extended format, Data Sources also processes the Referrer and the User Agent fields.

You can view web log data using standard marketing reports for Page Views, Visits, and Visitors. Because report metrics are primarily based on cookies, and web server logs are based on the IP address, Adobe recommends importing the web server logs into a separate report suite specifically for that purpose.

For more information about your web server log files, consult your web server documentation.

## Section Title {#section_6F9F2E0CBF5A48BCA7748E200763882F}

