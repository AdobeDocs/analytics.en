---
description: To activate the integration, you must complete the configuration wizard within the Data Connectors interface.
seo-description: To activate the integration, you must complete the configuration wizard within the Data Connectors interface.
seo-title: Completing the Adobe Integration Wizard
title: Completing the Adobe Integration Wizard
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
---

# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

To activate the integration, you must complete the configuration wizard within the Data Connectors interface.

1. Navigate to the Data Connectors (formerly Genesis) area within the Adobe Experience Cloud. 
1. Launch the Demandbase 2.0 integration wizard. 
1. Choose the desired Report Suite and provide a name for the integration. 
1. Configure the following items: 

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Email address </td> 
   <td colname="col2"> The primary contact's email address. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> (Optional) Description for this integration setup. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API key </td> 
   <td colname="col2"> You can obtain this from your Demandbase representative. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Custom Demandbase Dimension #N </td> 
   <td colname="col2"> These are the IDs for the 8 optional dimensions. For more information, see Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Send to Adobe Target </td> 
   <td colname="col2">If “true”, the Demandbase dimensions will also be sent to Adobe Target using a hidden mbox. <p>Note:  A configured mbox.js file must be implemented on the webpage for dimensions to be collected. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configure the following Variable Mappings items: 

   |  Item  | Description  |
   |---|---|
   |  Demandbase Dimensions  | Choose an available eVar variable from your report suite.  |
   |  Demandbase Custom Dimensions (optional)  | Choose an available eVar variable from your report suite.  |

1. Configure the names for the Custom Dimension (if applicable).

    1. If you chose to include Custom Dimensions in step 4 and mapped the optional eVar in step 5, then you have to provide friendly names for those dimensions. For example, if you chose to enter “stock_ticker” as Custom Dimension 1, then you should change the box containing “Dimension 1” to “Stock Ticker”. 
    1. Do **NOT** modify the names of the standard 8 dimensions (i.e. Demandbase SID, Company Name, Industry, etc.).

1. Check the box to have the Demandbase Integration dashboard automatically created for you (recommended). 
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

