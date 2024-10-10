---
description: Filters that apply specific dimension terms.
title: Specific filters
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
---
# Specific filters

Filters that apply specific dimension terms.

You can search on specific dimension items by creating a filter that matches exact criteria. For example, you can create the following type of filter: page in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**To create a Specific filter** 

1. Create or edit a request, and advance to the [!UICONTROL Request Wizard: Step 2].

   ![Screenshot showing the Filter by options: Application, User, and Project.](/help/admin/admin/assets/filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

1. Enable **[!UICONTROL Specific]**.

   ![Screenshot of the Choose Page dialogue with the Specific option selected.](assets/choose_page_specific01.png)

1. Enable one of the following Specific options:

   * **From Range of Cells:** Lets you select data from cells. You can select:
     * **All Cells in Range:** Lets you map every cell for the range. Descriptive text explains how many groups of cells you must select. To map more than one group of cell, press the ctrl key as you are making successive selections. If the range that must be mapped contains only one cell, this is the only available option 
     * **First Cell of Range:** You only need to select the upper left cell of the range, and then choose a direction for the data. Additionally, if the request has multiple periods, you choose the direction of the periods and choose whether you want to skip a set number of cells between periods.
   * **From List:** Lets you select data from a list to which you can add data.
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension items for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. On the [!UICONTROL Select From List], click **[!UICONTROL OK]**.
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.
