---
description: Steps to change the default visualization.
seo-description: Steps to change the default visualization.
seo-title: Configure the Dataset Schema Interface
solution: Analytics
title: Configure the Dataset Schema Interface
topic: Data workbench
uuid: a89d3f35-7a4f-4dd0-a9ec-fe20339d0626
index: y
internal: n
snippet: y
---

# Configure the Dataset Schema Interface

Steps to change the default visualization.

You can control which type of visualization displays when you click a dimension name in a [!UICONTROL Dataset Schema Interface] by adding files to the Profiles\*profile name*\Context\Dimension Legend folder of the Data Workbench server installation folder. The [!DNL Default.1d] file in this folder controls the default visualization type for all of the dimensions. By adding a *dimension name*.1d file (such as [!DNL Hour.1d]) to this folder, you can control the default visualization for that particular dimension.

For more information about [!UICONTROL Dataset Schema Interfaces], see [The Dataset Schema Interface](../c_admin_intrf/c_dtst_sch_intrf.md#concept_E147B3A5B542453CA2B121E1C85BB175).

**To change the default visualization ** 

1. In any workspace, create a visualization containing the data that you want to appear in the new default visualization.

   For example, if you want the dimension to display in a bar graph, create a bar graph visualization showing the desired metric and dimension. 

1. Right-click the top border of the callout window and click **[!UICONTROL Save]**.
1. In the [!UICONTROL Save] window, click  ![](assets/btn_folder_up.png), double-click **[!UICONTROL Context]**, then double-click **[!UICONTROL Dimension Legend]**.
1. In the [!UICONTROL File Name] field, type the dimension name.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. For example, [!DNL Hour.1d]. 

1. Change the file extension to “1d” and click **[!UICONTROL Save]**.

   The file is saved to the User\*working profile name*\Context\Dimension Legend folder.

   The next time that you click that dimension from in a [!UICONTROL Dataset Schema Interface], the visualization that you specified displays. 

1. (Optional) To make this change available to all users of the working profile:

    1. In the [!UICONTROL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Dimension Legend]**. 
    
    1. Right-click the check mark next to the file name of the new callout in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

