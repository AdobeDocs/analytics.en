---
description: Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like pop music terms and report on the success of that category relative to metrics like Instances (click-throughs), and conversion to success events.
seo-description: Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like pop music terms and report on the success of that category relative to metrics like Instances (click-throughs), and conversion to success events.
seo-title: Conversion classifications
solution: Analytics
subtopic: Classifications
title: Conversion classifications
topic: Admin tools
uuid: 0663176f-49f5-42a9-87e9-67fdc0df1451
index: y
internal: n
snippet: y
---

# Conversion classifications

Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like pop music terms and report on the success of that category relative to metrics like Instances (click-throughs), and conversion to success events.

## Conversion classifications {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Classifications are used to categorize values into groups and report at the group level. For example, you can classify all Paid Search campaigns into a category like *pop music terms* and report on the success of that category relative to metrics like Instances (click-throughs), and conversion to success events. 

Conversion classifications let you classify conversion variables. Once classified, any report that you can generate using the key data can also be generated using the associated data properties.

After enabling classifications, use the [Classification Importer](../c-classifications2/c-classifications-importer/c-working-with-saint.md#concept_08ED8C7A86C64E7DA5DE3044BB94B2EA) to assign specific values to the appropriate classification.

## Conversion Classifications Descriptions {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Name</span> </td> 
   <td colname="col2"> The classification name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Date Enabled (Text Only)</span> </td> 
   <td colname="col2"> <p>Indicates if the text classification is a date range for campaign variables. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Options (Text Only)</span> </td> 
   <td colname="col2">Creates a list of classification values available for this classification. Use <span class="wintitle"> Options</span> with campaign variables to provide users with a list of supported values for the classification in the <span class="wintitle"> Campaign Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number Type (Numeric Only)</span> </td> 
   <td colname="col2">Specifies the type of number in the numeric classification. Options include <span class="wintitle"> Numeric</span>, <span class="wintitle"> Percent</span>, and <span class="wintitle"> Currency</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Add conversion classifications {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Steps that describe how to add conversion classifications in Admin.

1. Click **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. From the **[!UICONTROL Select Classification Type]** drop-down list, select the variable where you want to add a classification.

   ![Step Info](assets/sub_class_create.png)

1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Add Classification]**.
1. In the **[!UICONTROL Select Type]** field, select the type of classification you want to add to the variable.

   Options include **[!UICONTROL Text]** and **[!UICONTROL Numeric]**. For more information on classification types, see [About Classifications](../c-classifications2/c-classifications.md#concept_4CEC7FF1A9E24204A7DA6B9AC70709DE). 
1. In the **[!UICONTROL Text Classifications]** dialog box, configure the classification as desired.

   See [Conversion Classifications Descriptions](../c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4) for information about these elements. 

1. In the **[!UICONTROL Dropdown List]** dialog box, add or remove options.

   Adding Options creates a list of classification values available for this classification. You can use this option with Campaign variables to provide users with a list of supported values for the classification in the Campaign Manager. Use this for classification dimensions where you have a small number of allowed values that rarely or never change. For example, you might run different campaigns aimed at different levels of customer loyalty: Silver, Gold, and Platinum. You could then use the drop-down list to ensure that the only values that are accepted are those that match your three levels. If anyone tries to use a different value, it gets discarded. 
1. Click **[!UICONTROL Save]**.

## Delete a conversion classification {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Delete a conversion classification when it is no longer needed.

1. Open the Report Suite Manager by clicking **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** in the Suite header.
1. Select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. From the **[!UICONTROL Select Classification Type]** drop-down list, select the variable where you want to delete a classification.
1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Delete Classification]**.
1. In the Delete Classification dialog box, click **[!UICONTROL Delete]**.
