---
description: The sidebar provides access to regularly-used functions and preserves visualizations as you move between Workspaces.
seo-description: The sidebar provides access to regularly-used functions and preserves visualizations as you move between Workspaces.
seo-title: Configure the sidebar
solution: Analytics
title: Configure the sidebar
topic: Data workbench
uuid: 90bef15a-f43e-4179-b73b-168aa4197d1e
index: y
internal: n
snippet: y
---

# Configure the sidebar

The sidebar provides access to regularly-used functions and preserves visualizations as you move between Workspaces.

 Administrators can customize a sidebar to make it appropriate for different user groups, then deploy the sidebar with a profile.

The sidebar is ideal to help you keep track of filters and local overrides. If you prefer not to use the sidebar, you can hide it.

## Add visualizations to the sidebar {#section_666F70A405DB4F8D8EAFFA567FFCAC06}

1. Launch Data Workbench. 
1. In the sidebar, click **[!UICONTROL Add]** > *< **[!UICONTROL item]**>*. For example, [!UICONTROL Selections Panel], [!UICONTROL Filters Panel], or [!UICONTROL Table].

   The following sidebar panels are available in the standard installation of Data Workbench. More items might be available in your specific profile:

    * **Selections Panel:** Lets you understand what selections are active in the current workspace. The [!UICONTROL Selections Panel] updates whenever you make a new selection. You can clear selections by clicking **[!UICONTROL x]**. See [Making Selections in Visualizations](../c_vis/c_sel_vis/c_sel_vis.md#concept_012870EC22C7476E9AFBF3B8B2515746) for information about how to select data. 
    * **Filters Panel:** Makes it easy to load and apply saved filters. You can load multiple filters, and enable or disable each one independently by clicking the check box next to it. See [Filter Editors](../c_analysis_vis/c_filter_editors/c_filter_editors.md#concept_2F343ECBED8240F18B0C1F1ECCEF11E3). 
    * **Local Override Panel:** This panel displays which metrics, dimensions, and filters that are present in the profile have been modified in your personal copy of the profile. This helps alert you to possible differences between the way data appears in your client and that of other users. When you save changes in a metric, dimension, or filter to the server, the override is removed from the [!UICONTROL Local Overrides panel]. If you click an override and then click **[!UICONTROL Revert to Server]**, the local override is removed and the item reverts to the shared version. 
    * **Metric Legend:** Adds a metric legend. [!UICONTROL Metric legends] enable you to see baseline metrics related to your profile and statistics related to the dataset (or to the current selection, if one has been made). See [Metric Legends](../c_analysis_vis/c_legends/c_metric_leg.md#concept_E7195BC8F7844AE295BDA3A88B028D5B). 
    * ****Color Legend:** Adds a color legend. You can color-code visualizations by metrics, such as Conversion and Retention, and use them in almost every [!UICONTROL Workspace]. Linking business metrics to color makes it easy to spot anomalies, exceptions, and trends. See [Color Legends](../c_analysis_vis/c_legends/c_color_leg.md#concept_F84D51DC0D6547F981D0642FC2D01358). ** 
    * **Text Annotation:** Adds a notes panel. [!UICONTROL Text annotations] are windows into which you can enter arbitrary text to add descriptive information or comments to a [!UICONTROL Workspace]. See [Working with Text Annotations](../c_analysis_vis/c_annots/c_text_annots.md#concept_55B4AA3E0C58470B8E3C9D452E12A777). 
    * **Table:** Adds a table. A table can display one or more metrics across one or more dimensions of data. See [Tables](../c_analysis_vis/c_tables/c_tables.md#concept_C632CB8AD9724F90AC5C294D52AE667F). 
    * **Open:** Opens a saved file.

## Open a Sidebar Panel {#section_CBC8E57491854274A577D47A48C306B8}

You can open a sidebar visualization file from a saved location or from the clipboard.

1. In the sidebar, click **[!UICONTROL Add]** > **[!UICONTROL Open]**. 
1. Click **[!UICONTROL File]** to locate the [!DNL .vw] file of the panel you want to add, or click **[!UICONTROL Last Closed Window]**, which pulls the visualization from the clipboard.

   Additionally, you can click **[!UICONTROL From Clipboard]** to paste a visualization that has been copied to the clipboard. See [Copying a Sidebar Panel](../c_get_started/c_config_sidebar.md#section_720AE057632A4B8DBB94412E06A370B1).

## Copying a Sidebar Panel {#section_720AE057632A4B8DBB94412E06A370B1}

1. Right-click the panel’s top border, then click **[!UICONTROL Copy]** > **[!UICONTROL Window]**. 
1. To paste the panel, click **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Saving a Sidebar Panel {#section_FB19936B12704FB0A4C592ABB579DB1D}

On an sidebar panel, right click in the title bar and click **[!UICONTROL Save]**.

Similarly, you can open a saved sidebar visualization. [!DNL Data workbench] saves the visualization as a [!DNL .vw] file at the location you specify.

## Revert to the Default Sidebar {#section_4D14B8771AD747BBA799876267F24831}

In the sidebar, click **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

When you close Data Workbench, the system saves the current sidebar configuration in the [!DNL sidebar.vw] file in the user profile. When you open Data Workbench, the system loads the [!DNL sidebar.vw] file from the user profile, rather than a parent profile.

You can revert to a default or previously saved sidebar, which deletes the sidebar from the user profile and reloads the sidebar from the parent profile. Administrators can replace the default (parent) sidebar with a local sidebar by uploading it from the [!UICONTROL Profile Manager].

## Customize the More Status Panel File {#section_8D502F3B59CC4331966EDEC05E896CE1}

System administrators can build formulas in the [!DNL More Status Panel.vw]. This places contextual words around metric and dimension values, and displays the results in the [!UICONTROL More Status panel] in the sidebar.

To display the [!UICONTROL More Status panel] in the sidebar, click the arrows shown in the following example.

![](assets/more_status_panel_arrows.png)

The following procedure shows a simple example of how to create a customized status that tells you how many days are in a dataset:

1. In the [!UICONTROL Profile Manager], click **[!UICONTROL Sidebar\]**. 

1. In the [!UICONTROL Base_5_3*] column, make a local copy of the [!DNL More Status Panel.vw] file.

   To do so, right-click the file check mark and click **[!UICONTROL Make Local]**. 

1. Open the [!DNL More Status Panel.vw] file in the [!DNL .vw] [!UICONTROL Editor] or in Notepad.

   ![](assets/more_status_panel_file.png)

1. Complete the [!UICONTROL Context] and [!UICONTROL Items] fields in the [!UICONTROL Editor]. See [Query Language Syntax](../c_qry_lang_syntx/c_qry_lang_syntx.md#concept_15D1D3F5164A47D49468C5ACB7299D9F) for guidelines about syntax. 

1. Save the file.

   The values in the preceding example result in a status formula displayed as follows:

   ![](assets/more_status_panel.png)

