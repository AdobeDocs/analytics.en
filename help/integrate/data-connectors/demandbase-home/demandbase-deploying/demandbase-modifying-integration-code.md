---
description: In most cases, you will not need to make any modifications to the integration code that is produced by the Data Connector wizard.
seo-description: In most cases, you will not need to make any modifications to the integration code that is produced by the Data Connector wizard.
seo-title: Modifying the Integration Code
title: Modifying the Integration Code
uuid: 3f49a29b-ad38-4967-894a-ef7ecf4d268f
index: y
internal: n
snippet: y
---

# Modifying the Integration Code{#modifying-the-integration-code}

In most cases, you will not need to make any modifications to the integration code that is produced by the Data Connector wizard.

However, if you do need to make adjustments, some of the code settings are described below. 

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">The maximum number of milliseconds that the Adobe Analytics image request will wait for the Demandbase data before firing off to the Analytics collection server. <p>Note:  This setting applies across all integrations that might be running through the Integrate Module. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._key </td> 
   <td colname="col2"> Your Demandbase API key. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._apiURL </td> 
   <td colname="col2"> The URL template for the Demandbase API. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._delim </td> 
   <td colname="col2"> The delimiter used to separate the Demandbase dimension values when they are sent to Adobe Analytics. Changing this setting may cause the default Classification Rules to not function correctly. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._setTnt </td> 
   <td colname="col2">If true, then the integration code will attempt to use a hidden mbox to send the Demandbase dimensions to Adobe Target as Profile Parameters. <p>Note:  This requires that the mbox.js code exists on the page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._tntVarPrefix </td> 
   <td colname="col2"> This string is prepended to each Demandbase dimension name before sending to Adobe Target. Example, if this setting has the value “db_” then the dimension “industry” will be sent to Adobe Target as “db_industry”. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._dimensionsArray </td> 
   <td colname="col2"> The standard Demandbase dimensions that are sent to Adobe Analytics. It is recommended that you do not modify this setting. The “max_size” property is the number of allowed characters for the dimension before truncation occurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._dimensionsArrayCustom </td> 
   <td colname="col2"> The custom Demandbase dimensions that are sent to Adobe Analytics. The “max_size” property is the number of allowed characters for the dimension before truncation occurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._cName </td> 
   <td colname="col2"> The name of the session cookie used to keep the state for the Demandbase API communication. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextName </td> 
   <td colname="col2"> The name of the contextData variable that is used to sent the standard dimensions to Adobe Analytics. It is recommended that you do not modify this setting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextNameCustom </td> 
   <td colname="col2"> The name of the contextData variable that is used to sent the custom dimensions to Adobe Analytics. It is recommended that you do not modify this setting. </td> 
  </tr> 
 </tbody> 
</table>

