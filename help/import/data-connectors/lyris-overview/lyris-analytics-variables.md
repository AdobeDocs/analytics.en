---
description: Describes the eVars and Events to be reserved for each report suite implementation.
seo-description: Describes the eVars and Events to be reserved for each report suite implementation.
seo-title: Configure Adobe Analytics variables for Lyris
solution: Analytics
title: Configure Adobe Analytics variables for Lyris
uuid: 12e150c4-052a-481c-8c27-ef45ee801977
index: y
internal: n
snippet: y
---

# Configure Adobe Analytics variables for Lyris{#configure-adobe-analytics-variables-for-lyris}

Describes the eVars and Events to be reserved for each report suite implementation.

This integration requires at least 2 eVars to be reserved for each report suite implementation. Apart from these eVars, a few events may be reserved depending on which Lyris data you would like to see in Analytics. These eVars and events are described in the table below: 

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> How the Variable is used </th> 
   <th colname="col4" class="entry"> Settings </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Message ID </td> 
   <td colname="col3"> To capture the individual email message campaign identification </td> 
   <td colname="col4"> <p>Status: Enabled </p> <p>Allocation: Most Recent </p> <p>Expire After: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> To capture the anonymous identification for your customer who clicked the email campaign </td> 
   <td colname="col4"> <p>Status: Enabled </p> <p>Allocation: Most Recent </p> <p>Expire After: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Emails Sent </td> 
   <td colname="col3"> To store no. of emails sent from Lyris </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Emails Opened </td> 
   <td colname="col3"> To store no. of emails that were opened </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Unique Emails Opened </td> 
   <td colname="col3"> To store no. of unique emails that were opened </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Click-throughs </td> 
   <td colname="col3"> To store no. of times any email was clicked </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Bounces </td> 
   <td colname="col3"> To store the no. of emails that were bounced </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Lyris - Email Unsubscribes </td> 
   <td colname="col3"> To store the no. of email subscriptions that were disabled </td> 
   <td colname="col4">Type: Numeric <p>Participation: Enabled </p> </td> 
  </tr> 
 </tbody> 
</table>

