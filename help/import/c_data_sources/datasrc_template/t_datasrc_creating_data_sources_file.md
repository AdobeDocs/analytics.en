---
description: The import template file is designed to get you started with the import.
seo-description: The import template file is designed to get you started with the import.
seo-title: Generate an import file template
solution: Analytics
subtopic: Data sources
title: Generate an import file template
topic: Developer and implementation
uuid: 0adb356a-1f32-4ff4-b6f0-252445e2bc5b
index: y
internal: n
snippet: y
---

# Generate an import file template

The import template file is designed to get you started with the import.

You are not limited to the columns defined in the template. You can add any additional columns as needed, as long as the metric or definition is supported for the selected data processing type. You can view the supported metrics and dimensions for each type in the following sections: [Web Log](../../c_data_sources/c_datasrc_types/datasrc_web_log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B), [Traffic](../../c_data_sources/c_datasrc_types/datasrc_traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC), [Conversion](../../c_data_sources/c_datasrc_types/datasrc_conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0), [Transaction ID](../../c_data_sources/c_datasrc_types/datasrc_transactionID.md#concept_A97302E9EC45468A8F30285FACE8C776), [Visitor ID](../../c_data_sources/c_datasrc_types/datasrc_visitorID.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5), [Full Processing](../../c_data_sources/c_datasrc_types/datasrc_full_processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../c_data_sources/c_datasrc_types/datasrc_traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

Once created, you can download the template, input your data into the template, then upload the data to the Data Sources FTP site. Once processed by the Data Sources server, the imported data is available for use in your SiteCatalyst reports.

The Data Source template is a .txt file that you can open with any text editor. However, it is easiest to work with the template using Microsoft Excel or another spreadsheet application. The template content varies based on your selections in the Data Source Activation Wizard.

See [Import File Reference](../../c_data_sources/datasrc_template/datasrc_import_file_reference.md#concept_472095E1D011434D98A21C101A4618BD) for additional details. 

1. Log in to Marketing Reports & Analytics.
1. In the Suite header, select **[!UICONTROL Admin Tools]** > **[!UICONTROL Data Sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   Step Result 1. Select template generation options in the Data Source Activation Wizard.

<table id="table_BE92DDFB21F4465EBE3E7582628875A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wizard Page </th> 
   <th colname="col2" class="entry"> Field </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Name </td> 
   <td colname="col3"> The template name that SiteCatalyst displays in The Data Sources Manager. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Email </td> 
   <td colname="col3"> The email address that receives all notifications related to the use of this Data Source template. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Associated Fees Checkbox </td> 
   <td colname="col3"> Select the check box to indicate your acceptance of the fees associated with using this Data Source template. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Choose Metrics </td> 
   <td colname="col3"> <p>Select the metrics to import using this Data Source. SiteCatalyst recommends certain metrics based on the Data Source Category and Type selected in Step 3. </p> <p>To specify a different metric, type its name in a blank field, then select the check box to enable the metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Map Metrics </td> 
   <td colname="col3"> <p>Select a SiteCatalyst Event to receive each imported metric selected in Wizard page 2. </p> <p>These should be new, unassigned Events that you have previously assigned names that correspond to the imported metric data they will receive through Data Sources. </p> <p>If an eVar, Product, or Tracking Code variable is a destination variable, and the uploaded values match existing captured values, the uploaded events essentially add metrics to existing values. For example, you might create an “Offline Orders” metric with a Products data dimension that already has Product Views, Checkouts, and Orders as existing metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Choose Data Dimensions </td> 
   <td colname="col3"> <p>Select the data dimensions to breakdown the imported metrics from this Data Source. SiteCatalyst recommends certain data dimensions based on the Data Source Type selected in Step 3. </p> <p>To specify a different data dimension, type its name in a blank field, then select the check box to enable the data dimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Map Data Dimensions </td> 
   <td colname="col3"> Select a standard report or eVar to receive each imported data dimension selected in Wizard page 4. </td> 
  </tr> 
 </tbody> 
</table>

1. After the template is generated, copy data into the appropriate columns of the Data Source template, making sure to adhere to the data format required for that data column.

   Step Result 1. Save the Data Sources file using a naming convention of your choice. Adobe recommends using a consistent naming convention for all Data Sources files. Use a common file extension such as .txt or .tsv (or don’t use any extension).

