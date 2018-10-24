---
description: Open functionality enables you to open such items as documents or URIs in such external applications as a text editor or a web browser.
seo-description: Open functionality enables you to open such items as documents or URIs in such external applications as a text editor or a web browser.
seo-title: Configure open functionality
solution: Analytics
title: Configure open functionality
topic: Data workbench
uuid: 1de41501-ccb6-4293-a693-a51d49de04d1
index: y
internal: n
snippet: y
---

# Configure open functionality

Open functionality enables you to open such items as documents or URIs in such external applications as a text editor or a web browser.

Open functionality is currently configured only in the [!UICONTROL Site] application and only for opening URIs. This section provides information about configuring Open URI functionality for [!UICONTROL Site]. For information about configuring Open functionality for another application or to open other items, contact Adobe Consulting Services.

In [!UICONTROL Site], you can right-click a URI from a page overlay or table to display the URI in the application for which it was formatted. For example, from a URI table visualization, you can click a URI to display a web page in a web browser.

To open a URI from a visualization, you first must edit the [!DNL Open URI.cfg] file for the URI dimension to identify the location and naming conventions that Data Workbench uses to open the URI. To view a URI in its native format (such as HTML), Data Workbench must have access to the referenced location and the application needed to open that item. For example, to view a web page, Data Workbench would need access to the Internet as well as have a web browser installed.

**To edit Open URI.vw**

1. In the [!UICONTROL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**. 
1. In the URI folder, right-click the check mark next to the [!DNL Open URI.vw]file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!UICONTROL User] column. 
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]** if the file is a [!DNL .cfg] file or **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** if it is a [!DNL .vw] file. 
1. Click **[!UICONTROL Command]**, then **[!UICONTROL Parameters]** to view the contents of the file. 
1. Modify the [!UICONTROL Site] parameter and the Template parameter as necessary:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this parameter... </th> 
   <th colname="col2" class="entry"> Provide this information... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>The location of the URIs that you want to open. </p> <p>Example: mysite.com </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Template </p> </td> 
   <td colname="col2"> <p>The parameters that Data Workbench should use to locate and open the URIs. </p> <p>Example: <span class="filepath"> http://%Site%%URI%</span> </p> <p>The default template shown in the example tells Data Workbench to open a web browser, look for the location defined in the <span class="wintitle"> Site</span> parameter, then locate the URI dimension element you are attempting to open. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file. 
1. To make this change available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!UICONTROL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

>[!NOTE]
>
>For instructions to open a URI in Data Workbench, see [Opening Next URIs from a Page Overlay](c_open_next_uri.md#concept_CADA5EFBD0204BE6BA6902F992079F58) and [Opening URIs from Tables](../../data-workbench-client/c-analysis-vis/c-tables/c-open-uri-tbls.md#concept_51EA9ED3937043E19505FBB82CB00233).

