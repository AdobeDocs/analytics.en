---
description: You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite
seo-description: You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite
seo-title: Browser import
solution: Analytics
subtopic: Classifications
title: Browser import
topic: Admin tools
uuid: d8402cca-e859-4f82-b255-3c7cf64674e0
index: y
internal: n
snippet: y
---

# Browser import

You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

You can import (upload) classifications data using the browser. This method limits your classification data upload to a single report suite 

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Classifications Browser Import - Field Descriptions {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Select Report Suite </td> 
   <td colname="col2"> <p>The report suite where you want to import the classifications data. The import data file must match the format of the data set in the report suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Set to be Classified </td> 
   <td colname="col2"> <p>The data set to receive the classifications. The drop-down list includes all reports in your report suites that are configured for classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Select file to Import </td> 
   <td colname="col2"> <p>Lets you browse to locate the import data file you want to upload. </p> <p>Note:  The upload file size limit is 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Overwrite Data on Conflicts </td> 
   <td colname="col2"> <p>Automatically overwrites existing data that conflicts with the imported data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Automatically Download Classification File After the Import is Complete </td> 
   <td colname="col2"> <p>Automatically downloads a tab-delimited file that represents the data set with the newly uploaded classifications data. Adobe automatically generates this file for you if the import creates any unique IDs, or if any errors occur. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Import classifications via the browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**.
1. Configure the [Browser Import](browser_export.md#concept_3D930F03840A491D8B37FAAE9C90F5DF) fields.
1. Click **[!UICONTROL Import File]**.
1. Watch the status window for processing messages.
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes.
>A successful import immediately displays the appropriate changes in an export. However, data changes in reports take up to four hours when using a browser import and up to 24 hours when using an FTP import. 

