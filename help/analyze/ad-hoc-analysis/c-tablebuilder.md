---
description: Use the Table Builder to create a report with any configuration of metrics, dimensions, and segments. For example, you can add multiple metrics to the Table Builder, then apply segment to all of them at once. You can apply items from the tool panes as rows and breakdowns, or as columns, and easily pivot the table for a different view. After building the table, you can interact directly with the resulting data table for further analysis. Keep in mind that generating a data table from the Table Builder runs a query and creates a new data table.
title: Table Builder
uuid: d5dbd05e-9ebd-4571-b3a5-3856c28b65f3
---

# Table Builder

>[!IMPORTANT]
>
>Adobe is moving Ad Hoc Analysis to end of life on March 1, 2021. [Learn more](https://adobe.ly/discoverworkspace)

Use the Table Builder to create a report with any configuration of metrics, dimensions, and segments. For example, you can add multiple metrics to the Table Builder, then apply segment to all of them at once. You can apply items from the tool panes as rows and breakdowns, or as columns, and easily pivot the table for a different view. After building the table, you can interact directly with the resulting data table for further analysis. Keep in mind that generating a data table from the Table Builder runs a query and creates a new data table.

## Table Builder {#concept_574FEDC73B244101935D3C86C39DB70F}

Use the Table Builder to create a report with any configuration of metrics, dimensions, and segments. For example, you can add multiple metrics to the Table Builder, then apply segment to all of them at once. You can apply items from the tool panes as rows and breakdowns, or as columns, and easily pivot the table for a different view. After building the table, you can interact directly with the resulting data table for further analysis. Keep in mind that generating a data table from the Table Builder runs a query and creates a new data table.

The [!UICONTROL Table Builder] is not available for certain pathing reports like [!UICONTROL Site Analysis], [!UICONTROL Fallout], [!UICONTROL Flow] and [!UICONTROL Virtual Focus].

## Table Builder Descriptions {#section_4B7B96546B864142AB91DF3996918590}

<table id="table_C11D78E62DEF48A78B50EFB8669817BC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Rows / Breakdowns</span> </td> 
   <td colname="col2"> <p>Creates rows and breakdowns from added items. The first item you drag to <span class="wintitle"> Rows / Breakdowns</span> becomes the left column in the data table, or the parent item in a breakdown. Adding subsequent items creates breakdowns. </p> <p>For example, if you add Page and then Cities dimensions, the report breaks down the page by cities. You configure how many rows and breakdowns to show for each item, using the following menus: </p> 
    <ul id="ul_702F215DFB814398B8F1879EDFEC103F"> 
     <li id="li_95C4DF2B33524C94BBD2E07397393300"> <span class="uicontrol"> Show</span> and <span class="uicontrol"> Breakdown</span>: Lets you specify the number of items and breakdowns to display. </li> 
     <li id="li_D594C7F31A094D1EA1A070B80794E006"> <span class="uicontrol"> Default</span>: Uses the settings configured in <span class="wintitle"> Breakdown Properties</span>. </li> 
    </ul> <p>You can also configure a fixed value list to, for example, break down one metric by multiple metrics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Breakdown Properties</span> </td> 
   <td colname="col2"> <p><img placement="inline"  src="assets/Settings_Illustrative.png" id="image_C46860621CF94E88AF592B8660F28E57"> </img> </p> <p>Lets you specify default settings for how many rows and breakdowns you want displayed, based on the order in which you add items. You can specify how many total results per page to display, and how many of those rows to break down. </p> <p>Settings you make in the <span class="wintitle"> Table Builder</span> override the default settings in the <span class="wintitle"> Breakdown Properties</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit Items</span> </td> 
   <td colname="col2"> <p><img  src="assets/Edit_Buttcon.png" id="image_E44BCC4B0BFF453D8564047E3DA2501A"> </img> </p> <p>Choose a list of dimension items to create a fixed list for breakdowns. When you add items to this list, they become persistent in a saved report and will not be collapsed when you open a saved or scheduled report. </p> <p>See <a href="/help/analyze/ad-hoc-analysis/c-reports-configure.md#task_29BEE0AF09DA4625B9B44BAB77D7C841"  > Break Down Table Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Columns</span> </td> 
   <td colname="col2"> <p>Lets you build columns with items from dimensions, segments, and metrics. You can also pivot the columns using the arrow icon, which pivots the X and Y axes. </p> <p> <span class="uicontrol"> Show</span>: Lets you limit the number of columns generated in the data table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Summary</span> </td> 
   <td colname="col2"> <p>Shows the report's structural layout so that you know how many rows and columns will be created. The summary reflects the configuration specified in the <span class="uicontrol"> Rows / Breakdowns</span> and <span class="uicontrol"> Columns</span> groups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Replace Table</span> </td> 
   <td colname="col2"> <p>Builds (and overrides) the existing table, based on your <span class="wintitle"> Table Builder</span> configuration. </p> <p>Note: Clicking <span class="uicontrol"> Replace Table</span> reruns the report and overrides the data in the table grid. If you add items to the table grid, the correlation between the table and the <span class="wintitle"> Table Builder</span> is no longer valid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Warning </td> 
   <td colname="col2"> <p><img id="image_619E1068C6084D41853DA3DD6B85DFC9"  src="assets/AlertRed_Illustrative.png" placement="inline" /> </p> <p>Indicates that the <span class="wintitle"> Table Builder</span>'s configuration will not return data, or that no metrics are selected. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generate a report from the Table Builder {#task_B04801AC9848485C93DF02E96C9A9902}

Steps that describe how to use the [!UICONTROL Table Builder].

<!-- 

t_table_builder.xml

 -->

1. To access the [!UICONTROL Table Builder], run a supported report, then click **[!UICONTROL Table Builder]**.
1. Drag items (dimensions, metrics, segments) from the tool panes to the [!UICONTROL Table Builder].
1. Configure the items as rows, breakdowns, and columns.
1. Click **[!UICONTROL Replace Table]** to generate the report.

   Clicking **[!UICONTROL Replace Table]** runs a new query and creates a new data table. Manual edits to the detail table are not reflected in the Table Builder.

