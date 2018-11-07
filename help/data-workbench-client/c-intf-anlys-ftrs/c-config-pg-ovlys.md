---
description: Page overlays are configured only in the Site application, but they can be configured for other applications.
seo-description: Page overlays are configured only in the Site application, but they can be configured for other applications.
seo-title: Configure a page overlay
solution: Analytics
title: Configure a page overlay
topic: Data workbench
uuid: 8aaaa2b0-79b3-4f80-bb3d-de2e786b98c8
index: y
internal: n
snippet: y
---

# Configure a page overlay

Page overlays are configured only in the Site application, but they can be configured for other applications.

 For information about configuring page overlay for another application, contact Adobe Consulting Services.

The page overlay visualization is a tool for HTML link analysis. When you request an overlay for a particular page, Data Workbench takes a snapshot of the actual page as it would appear in a web browser and parses the HTML code that represents links according to a list of regular expressions that you define. For each link on the selected page, the software attempts to find a regular expression pattern match by working down the list until the first match is found. If there is a match, the link appears highlighted in the page overlay.

Page overlay shows data only when you add a color legend to the workspace containing the page overlay. For information about using page overlays for analysis, see [Page Overlays](c_pg_overlays.md#concept_4BD5BFB17791426EB1BFF4A25B6864BB).

>[!NOTE]
>
>Configuring page overlay requires careful configuration work, and it is possible to create misleading results if links are inappropriately mapped to the data. The work involved in configuring page overlay for a specific site depends on how links are presented within the HTML code on the site’s pages.

Page overlay, by its nature, suggests to the user the mental model that it displays “where people click.” If the data backing the visualization does not match this model, the potential for confusion is high.

In [!UICONTROL Site], a link typically represents an element from the Next URI or Next Link dimension, but you can map a link to any dimension that makes sense for your analysis. For information about configuring page overlay for other dimensions, contact Adobe Consulting Services.

>[!NOTE]
>
>Using the Page dimension for page overlay is not recommended. Users can rename the elements of the Page dimensions, thereby altering the link syntax on which the page overlay functionality relies.

To configure page overlay for [!UICONTROL Site], you must edit two files:

* **[!DNL Page Overlay.vw]:** This file is a template file for creating page overlay visualizations. At least one template file must be present in the profile for which you are configuring page overlay. 
* **[!DNL Page Overlay Link Templates.cfg]:** When the page overlay visualization loads a page, it automatically identifies the links in the page and their destinations. To relate these links to elements in the data, you must define a set of regular expressions in this file.

  You can define multiple regular expressions to match against the elements of the dimension. The order in which you define the expressions is important. When you request an overlay for a particular page, Data Workbench takes a snapshot of the actual page as it would appear in a web browser and parses the HTML code that represents links according to a list of regular expressions that you define. For each link on the selected page, the software attempts to find a regular expression pattern match by working down the list until the first match is found. The first expression to match a dimension element is the one used. Therefore, it is best to list the regular expression with the most specific matching pattern first, followed by less specific expressions. If there is a match, the link appears highlighted in the page overlay visualization.

**To configure page overlay for Site**

1. I

   n the [!UICONTROL Profile Manager], navigate to **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >The Dimension Element directory contains the context menu items that appear when you right-click a dimension element. For example, open a URI table, then select a URI element. Right-click the URI and Page Overlay appears.

1. In the URI folder, right-click the check mark next to the [!DNL Page Overlay.vw] file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!UICONTROL User] column. 
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 
1. Specify the Domain (and Browser Height, if required).

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: https://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. Save the file. 
1. To make this change available to all users of the working profile, in the [!UICONTROL Profile Manager], right-click the check mark for the [!DNL .vw] file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >You can create additional template files for other sites or subdomains. Each template that you create appears in the [!UICONTROL Page Overlay menu].

1. In the Context folder of the [!UICONTROL Profile Manager], right-click the check mark next to the [!DNL Page Overlay Link Templates.cfg] file and click **[!UICONTROL Make Local]**.

   A check mark for this file appears in the [!UICONTROL User] column. 

1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 
1. Right-click **[!UICONTROL Link Templates]** and click **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**. 
1. Edit the parameters for LinkRegex vector as necessary:

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Dimension </p> </td> 
   <td colname="col2"> <p>The dimension (typically the Next URI dimension) that is represented by the link. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Expression </p> </td> 
   <td colname="col2"> <p>The regular expression used to select the relevant part of the HTML link to find the next element from the Dimension. The regular expression must be an exact match, and the desired output pattern is grouped with parentheses. For details about regular expressions, see the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Output Pattern </p> </td> 
   <td colname="col2"> <p>The output pattern of the regular expression used to extract the resulting element of the Dimension parameter. </p> </td> 
  </tr> 
 </tbody> 
</table>

   The following sample file shows three regular expressions:

   ![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
1. To make this change available to all users of the working profile, right-click the check mark for [!DNL Page Overlay Link Templates.cfg] in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

For instructions to create a configured page overlay in Data Workbench, see [Creating a Page Overlay](c_create_pg_overlay.md#concept_6ADA51C6CFB0426298688DCD64340CD5). 
