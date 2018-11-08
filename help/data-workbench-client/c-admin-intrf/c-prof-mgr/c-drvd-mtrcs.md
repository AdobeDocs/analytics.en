---
description: You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.
seo-description: You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.
seo-title: Work with derived metrics
solution: Analytics
title: Work with derived metrics
topic: Data workbench
uuid: 2bbac4bd-0863-4fc4-bddf-02cab0386803
index: y
internal: n
snippet: y
---

# Work with derived metrics

You define new metrics (referred to as derived metrics) and edit existing metric definitions using the Metric Editor.

For more information about metrics than is provided in this section and in [Query Language Syntax](../../../data-workbench-client/c-qry-lang-syntx/c-qry-lang-syntx.md#concept_15D1D3F5164A47D49468C5ACB7299D9F), see the *Metric, Dimensions, and Filters Guide*.

## Create a derived metric {#section_D57B98BF0A9940DABA4920FF7EFC808D}

You use a [!UICONTROL Metric Editor] to define a new metric by name, formula, and format, which is saved to the User\*profile_name*\Metrics folder for later use.

1. Open a new [!UICONTROL Metric Editor] using the **[!UICONTROL Admin]** > **[!UICONTROL Profile]** menu option or by right-clicking the **[!UICONTROL User]** column for the folder in which you want to create the metric and clicking **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   A [!UICONTROL Metric Editor] displays. 

1. In the Name parameter, type a name for the new metric.

   Note that spaces ( ) are allowed while underscores (_) are not. In addition, you cannot use the following symbols:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. In the Formula parameter, type an expression for the new metric. Note that filters must be defined within brackets [ ] in the expression.

   For additional metric expression syntax rules, see [Syntax for Metric Expressions](../../../data-workbench-client/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept_BBF440A0307549E088DF491B51B51D66).

   The following table provides sample expressions for extended metrics.

    <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
     <thead> 
      <tr valign="top"> 
       <th colname="col1" class="entry"> Extended Metric Name </th> 
       <th colname="col2" class="entry"> Expression </th> 
      </tr>
     </thead>
     <tbody> 
      <tr valign="top"> 
       <td colname="col1"> <p>Percent First Sessions </p> </td> 
       <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
      </tr> 
      <tr valign="top"> 
       <td colname="col1"> <p>Conversion First Sessions </p> </td> 
       <td colname="col2"> <p><span class="filepath"> Conversion [Session_Number="1"]</span> </p> </td> 
      </tr> 
      <tr valign="top"> 
       <td colname="col1"> <p>Average Value Per Visitor </p> </td> 
       <td colname="col2"> <p><span class="filepath"> Value/Visitors</span> </p> </td> 
      </tr> 
     </tbody> 
    </table>

   >[!NOTE]
   >
   >When an appropriate expression is entered, the preview line displays the value of the new metric. If there is an error in the expression, the preview line displays an error message.

1. Right-click **[!UICONTROL (New)]** and click **[!UICONTROL Save]**.

   When you save the metric, a file representing the new metric is created on your computer in the Data Workbench Installation directory \User\*profile name*\Metrics folder.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

You now can use the new metric throughout the current profile by selecting it as you would any built-in metric. To change the order in which your metrics appear on the metrics menu, see [Customizing Menus Using Order.txt Files](../../../data-workbench-client/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task_A391800A8DD444DEB3E1516D5189F999).

If you would like all users of the profile to use the metric that you created, you must publish it to the working profile using the [!UICONTROL Profile Manager]. See [Publishing Files to Your Working Profile](../../../data-workbench-client/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task_A0106E010C834D16BD60EEF4721B6AF9).

## Edit a derived metrics {#section_DB6D924CF4E14BCC8D57CFE1059FC797}

1. In the [!UICONTROL Profile Manager] or [!UICONTROL Metrics Manager], in the *profile name* column, right-click the check mark for the metric file that you want to edit, then click **[!UICONTROL Make Local]**. 
1. Right-click the check mark for the metric file in the [!UICONTROL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >You also can open a [!UICONTROL Metric Editor] by right-clicking any metric-related area within a visualization to display the metric menu. For more information, see [Working with Metric and Dimension Menus](../../../data-workbench-client/c-vis/c-met-dim-menus.md#concept_50F07AE47C3E4F94AD7D3D7F8293CCAC).

1. In the [!UICONTROL Metric Editor], edit and save the metric definition as necessary using Steps 2-4 in [Creating New Derived Metrics](../../../data-workbench-client/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section_D57B98BF0A9940DABA4920FF7EFC808D).

   If you would like all users of the profile to use the metric that you edited, you must publish it to the working profile using the [!UICONTROL Profile Manager]. See [Publishing Files to Your Working Profile](../../../data-workbench-client/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task_A0106E010C834D16BD60EEF4721B6AF9).
