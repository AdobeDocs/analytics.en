---
description: The Data Connectors integration for emarsys uses Analytics variables to track various emarsys metrics.
title: Analytics Variables
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
exl-id: a59216f2-047b-429b-8714-a2bdaa271911
---
# Analytics Variables{#analytics-variables}

The Data Connectors integration for emarsys uses Analytics variables to track various emarsys metrics.

After identifying the Event and eVars to use with the emarsys integration, enable them in the [Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/c-admin-tools.html).

**Required Variables** 

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Name </th> 
   <th colname="col3" class="entry"> Population Method </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event (numeric) </td> 
   <td colname="col2"> Total Bounces </td> 
   <td colname="col3"> <p>Automatically imported from emarsys </p> </td> 
   <td colname="col4"> <p>The Total Bounces event lets you see the number of email messages that were not delivered to recipients due to a delivery problem. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numeric) </td> 
   <td colname="col2"> Clicked </td> 
   <td colname="col3"> <p>Automatically imported from emarsys </p> </td> 
   <td colname="col4"> <p>The Clicked event lets you see the number of visitors who clicked the email message. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numeric) </td> 
   <td colname="col2"> Opened </td> 
   <td colname="col3"> <p>Automatically imported from emarsys </p> </td> 
   <td colname="col4"> <p>The Opened event lets you see the number of visitors who opened the email message. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numeric) </td> 
   <td colname="col2"> Sent </td> 
   <td colname="col3"> <p>Automatically imported from emarsys </p> </td> 
   <td colname="col4"> <p>The Sends event lets you see the number of email messages that were sent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numeric) </td> 
   <td colname="col2"> Unsubscribed </td> 
   <td colname="col3"> <p>Automatically imported from emarsys </p> </td> 
   <td colname="col4"> <p>The Unsubscribed event lets you see the number of visitors who opened the email but then clicked the Unsubscribe link to opt-out of future email messages from your organization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Collected from query parameters in email links through the automated collection method or a JavaScript plug-in. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar or s.campaign </td> 
   <td colname="col2"> Message ID </td> 
   <td colname="col3"> <p>Collected from query parameters in email links through the automated collection method or a JavaScript plug-in. </p> </td> 
   <td colname="col4"> This value is often stored in the campaign variable. </td> 
  </tr> 
 </tbody> 
</table>
