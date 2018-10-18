---
description: Steps to make any vector layer available to display on the globe visualization.
seo-description: Steps to make any vector layer available to display on the globe visualization.
seo-title: Make a new vector layer available
solution: Analytics
title: Make a new vector layer available
topic: Data workbench
uuid: 664a4547-c5f3-4eb0-8c9e-7a3e04b17bab
index: y
internal: n
snippet: y
---

# Make a new vector layer available

Steps to make any vector layer available to display on the globe visualization.

1. In the Profiles\*profile name*\Maps folder within the Data Workbench server installation directory, place the layer file and the [!DNL .vec] or [!DNL .tsv] files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. By default, layers appear in lexicographic order by their names.

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see [Customizing Menus Using Order.txt Files](../../c_intf_anlys_ftrs/c_ctm_menus/t_cstm_menus_ordr_files.md#task_A391800A8DD444DEB3E1516D5189F999). 

1. In Insight, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *< **[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. An X appears next to Work Online.
1. Open a workspace and on a globe visualization, right-click and select the new layer. An X appears next to the layer name.
