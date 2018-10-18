---
description: A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports.
seo-description: A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports.
seo-title: About classifications
solution: Analytics
subtopic: Classifications
title: About classifications
topic: Admin tools
uuid: 73487379-906f-4a8d-8b92-47a86e9afe88
index: y
internal: n
snippet: y
---

# About classifications

A classification is a way of categorizing Analytics variable data, then displaying the data in different ways when you generate reports.

Video overview of [Analytics Classifications](https://video.tv.adobe.com/v/16853/).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

When classifying, you are establishing a relationship between the variable and the metadata related to that variable. Classifications are most frequently used in campaigns. Data collected using variables (eVars, props, and events) information can be rolled up by applying metadata to the values collected in the variables.

![Step Info](assets/sub_class_create.png)

Once classified, any report that you can generate using the key variable can also be generated using the associated attributes. For example, you can classify [!UICONTROL Product IDs] with additional product attributes, such as product name, color, size, description, and SKU. Augmenting reporting and analytics data with additional attributes provides deeper and more complex reporting opportunities.

>[!NOTE]
>
>In the May 10, 2018, Analytics Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. These classification types were removed from the Admin and Classification Importer interfaces. No new date-enabled and numeric classifications can be added. Existing classifications can still be managed (uploaded to, deleted) through the standard classification workflow, and will continue to be available in reporting.

After creating the classifications, you can leverage the new data attributes throughout Adobe Analytics.

**Tracking Codes Example**

Suppose that instead of viewing campaigns just by the tracking code, you want to see campaign results by Search Engine, Keyword, and Campaign Channel. Rather than devoting conversion variables for each of those, you can create three classifications of the campaign variable to represent Search Engine, Keyword, and Campaign Channel. This strategy allows you to see site success events by all four variables, with no additional tagging.

Reporting and analytics includes pre-defined classifications for the tracking code variable, which offers classification-based reports called Creative Elements and Campaigns. You must manually configure classifications for all other conversion and traffic variables.

See [Traffic Classifications](../c_classifications2/traffic_classifications.md#concept_028079B29A9C412AA68910A87E11176F) and [Conversion Classifications](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=conversion_classifications).

The following table describes the different types of classifications that are available, and the variable types that support them. Review the information in [General File Structure](../c_classifications2/c_classifications_importer/c_saint_data_files.md#concept_9EFF968DF5D244A887DE94075431C1BE) before uploading data files. 

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>TYPE </p> </th> 
   <th colname="col2" class="entry"> <p>AVAILABILITY </p> </th> 
   <th colname="col3" class="entry"> <p>DESCRIPTION </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Text</span> </p> </td> 
   <td colname="col2"> <p>Conversion and Traffic Variables </p> </td> 
   <td colname="col3"> <p>Text classifications define a category that lets you group variable data for reporting purposes. </p> <p>For example, if you sell shirts, you might want to categorize shirt sales (conversions) by color, size, and style so you can generate reports that let you see shirt sales organized by these categories. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Date Enabled Text</span> </p> <p>Note:  In the May 10, 2018, Analytics Maintenance release, Adobe started to limit the functionality of date-enabled. These classification types were removed from the Admin and Classification Importer interfaces. No new date-enabled classifications can be added. Existing classifications can still be managed (uploaded to, deleted) through the standard classification workflow, and will continue to be available in reporting. </p> </td> 
   <td colname="col2"> <p>Conversion Variables </p> </td> 
   <td colname="col3"> <p>A date-enabled text classification lets you assign date ranges to a text classification. This is typically used with campaign classifications so that you can take advantage of the Gantt chart view in the <span class="wintitle"> Campaigns</span> report. </p> <p>You can include the actual campaign dates in the data file that populates the classification data. </p> <p>Reports &amp; Analytics collects campaign tracking codes even if the campaign end date is already past, but the campaign data collected after the end date of the campaign is not associated with the campaign. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Numeric</span> <p>Note:  In the May 10, 2018, Analytics Maintenance release, Adobe started to limit the functionality of numeric classifications. These classification types were removed from the Admin and Classification Importer interfaces. No new numeric classifications can be added. Existing classifications can still be managed (uploaded to, deleted) through the standard classification workflow, and will continue to be available in reporting. </p> </p> </td> 
   <td colname="col2"> <p>Conversion Variables </p> </td> 
   <td colname="col3"> <p>Numeric classifications let you apply fixed numeric values to <span class="wintitle"> Conversion</span> reports. These classifications appear as metrics in reports. </p> <p>When considering whether to add a <span class="wintitle"> Numeric</span> classification, the numeric value must be fixed and unchanging over time. </p> </td> 
  </tr> 
 </tbody> 
</table>

