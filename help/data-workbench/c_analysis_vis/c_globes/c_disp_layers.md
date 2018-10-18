---
description: The Geography profile stores a collection of imagery layers and files.
seo-description: The Geography profile stores a collection of imagery layers and files.
seo-title: Display layers
solution: Analytics
title: Display layers
topic: Data workbench
uuid: 9d79ed00-f4e7-4705-a15e-b3dcdb1fd0f6
index: y
internal: n
snippet: y
---

# Display layers

The Geography profile stores a collection of imagery layers and files.

 When you display a globe, you can select which of the available layers to display for a particular analysis task:

* **Blue Marble 2km:** This layer displays the globe. When this layer is not selected, the globe is not visible. 
* **IP Coordinates:** This element point layer displays the latitude and longitude of locations in your dataset based on visitor IP addresses. 
* **Zip Points:** This layer displays the latitude and longitude of locations in your dataset based on a list of United States ZIP Codes provided by Adobe. The [!DNL Zip Points.txt] lookup file contains the ZIP Code, latitude, and longitude data to be displayed, while the [!DNL Zip Points.layer] file contains the configuration parameters needed to display this data on the globe. Both of these files are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory. 

* ***Other available layer names:*** Each layer name represents a [!DNL .layer] file stored in the Profiles\Geography\Maps folder, Profiles\IP Geo-location\Maps folder, or Profiles\IP Geo-intelligence\Maps folder within the Insight Server installation directory.

>[!NOTE]
>
>To have the IP Geo-location or IP Geo-intelligence profile, you must subscribe to either the IP Geo-location or IP Geo-intelligence data service, respectively.

To control the order in which your layers display, you can use an [!DNL order.txt] file. See [Customizing Menus Using Order.txt Files](../../c_intf_anlys_ftrs/c_ctm_menus/t_cstm_menus_ordr_files.md#task_A391800A8DD444DEB3E1516D5189F999).

**To toggle layers in a globe**

* Right-click within the visualization and click the desired layer name. An X to the left of the layer indicates that the layer is visible.

