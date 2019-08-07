---
description: This integration requires 2 eVars to be reserved for each report suite implementation.
seo-description: This integration requires 2 eVars to be reserved for each report suite implementation.
seo-title: Configure Analytics Variables for Selligent
solution: Analytics
title: Configure Analytics Variables for Selligent
uuid: 3b7b8b4b-7614-4439-bcb0-dbdec5304844
index: y
internal: n
snippet: y
---

# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

This integration requires 2 eVars to be reserved for each report suite implementation.

Apart from these eVars, a few events may be reserved depending on the data from Selligent, which you would like to see in Analytics. These eVars and events are described as below: 

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Type </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> How it is Used </th> 
   <th colname="col4" class="entry"> Settings </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Message ID </td> 
   <td colname="col3"> To capture the individual email message campaign identification. </td> 
   <td colname="col4"> <p><b>Status</b>: Enabled </p> <p><b>Allocation</b>: Most Recent </p> <p><b>Expire After</b>: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> To capture the anonymous identification for your customer who clicked the email campaign. </td> 
   <td colname="col4"> <p><b>Status</b>: Enabled </p> <p><b>Allocation</b>: Most Recent </p> <p><b>Expire After</b>: “Business Decision” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Sent </td> 
   <td colname="col3"> To store the number of emails sent from Selligent. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Delivered </td> 
   <td colname="col3"> To store the number of emails that were delivered. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Views </td> 
   <td colname="col3"> To store the number of unique emails that were viewed. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Clicks </td> 
   <td colname="col3"> To store the number of times any email was clicked. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> Bounced </td> 
   <td colname="col3"> To store the number of emails that were bounced. </td> 
   <td colname="col4"> <p><b>Type</b>: Numeric </p> <p><b>Participation</b>: Enabled </p> </td> 
  </tr> 
 </tbody> 
</table>

