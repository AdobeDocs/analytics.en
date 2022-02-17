---
description: Create, manage, and view the use of data sources in a report suite.
subtopic: Data sources
title: Data Sources Manager
topic-fix: Developer and implementation
feature: Data Sources
exl-id: a63137b8-deeb-4865-9be9-322416b00186
---
# Data Sources Manager

Create, manage, and view the use of data sources in a report suite.

 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.

## Create Tab {#section_74603FDA3D8842E49F1A51624A06DE20}

The [!UICONTROL Create] tab lets you configure a new data source for the currently selected report suite. When you activate a data source, the [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

The selection you make on the Create tab determines the initial fields in the template that is created. See [Generating an Import File Template](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md).

## Manage Tab {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Restart Processing </p> </td> 
   <td colname="col2"> <p>Restarts data source processing that previously stopped due to errors or warnings. Processing continues until the next error is encountered. Data Sources halts processing of a Data Sources file only when you select <span class="uicontrol"> Stop Processing on Errors</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Complete Processing </p> </td> 
   <td colname="col2"> <p>Instructs Data Sources to close any open visits in the file and finish processing of the Data Sources file as if it is complete. This is useful when you have visits that span multiple Data Sources files. This applies only to <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Full Processing</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deactivate </p> </td> 
   <td colname="col2"> <p> Deactivating a Data Source will delete it. If any files on the server have begun to process, that processing will continue until complete. Files that have not yet begun processing will not be processed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop processing on errors/warnings </p> </td> 
   <td colname="col2"> <p> Instructs the Data Sources Processing Engine to stop processing when it encounters an error. The data source does not resume processing until you select Restart Processing. The Stop processing on warnings option applies only to <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Full Processing</a>. </p> <p>When Data Sources encounters a file error, it notifies you of the error. The system moves the Data Sources file with the error into a folder called <span class="filepath"> files_with_errors</span> on the FTP server. After you have resolved the problem, resubmit the Data Sources file for processing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure </p> </td> 
   <td colname="col2"> <p>Lets you modify the data source template, or other settings specific to this data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP Info </p> </td> 
   <td colname="col2"> <p>Displays the FTP information for this data source. Use this information to access the data source template, and send Data Source data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Name </p> </td> 
   <td colname="col2"> <p>The name of the file uploaded </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p> The current status of the file. Possible status values include the following: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">In Queue (step 1 of 3): The file exists, but has not begun processing. If the file doesn't appear within 30 minutes, check that the associated <span class="filepath"> .fin</span> file is present </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">Preparing (step 2 of 3): The file is being checked for errors or warnings </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">Processing (step 3 of 3): The file is being processed </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Failed: The file was not processed due to errors </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Success: The file was completely processed </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## File Log Tab {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

The file log includes a search feature that lets you search for information by Data Source Name, Data Source Type, file name, date received, or status.
