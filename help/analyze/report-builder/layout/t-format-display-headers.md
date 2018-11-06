---
description: You can name your report and configure how to display row and column headers. The Format Options link is available for the Pivot and Custom Layout types.
seo-description: You can name your report and configure how to display row and column headers. The Format Options link is available for the Pivot and Custom Layout types.
seo-title: Format display headers
solution: Analytics
title: Format display headers
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
index: y
internal: n
snippet: y
---

# Format display headers

You can name your report and configure how to display row and column headers. The Format Options link is available for the Pivot and Custom Layout types.

1. Create a request on the [!UICONTROL Request Wizard: Step 1].
1. Click **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Click **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

    <table id="choicetable_956FE9AB50664FC784ACAACAE0FD66F7"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Element</th> 
  <th class="chdeschd"> Description</th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Report Name</strong></td> 
  <td class="chdesc stentry">Displays either the name of the report type you selected from the tree in the <span class="wintitle"> Request Wizard: Step 1</span> (for example, <span class="wintitle"> Traffic Report</span>), or the name you type in the <span class="wintitle"> Name this Request</span> field. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Filters Parameters</strong></td> 
  <td class="chdesc stentry"> Displays the dimension filters, such as a search filter.</td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Segment</strong></td> 
  <td class="chdesc stentry"> Displays the segment parameter.</td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Data Recency</strong></td> 
  <td class="chdesc stentry"> <p>Displays data recency parameters. For example: </p> <p> <span class="codeph"> Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)</span> </p> <p>See <a href="../../../analyze/report-builder/options.md#concept_1372C99601BA4FE4A27DDACA39D8FB2D" format="dita" scope="local"> Options</a> for information about current data processing. </p> </td> 
 </tr> 
</table>

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   ** Display Row and Column Headers:** Adds a row and column to display these items.

   In version 3.11, you could display a header for each item. Version 4 displays all of these items or none of them. If you created a request in version 3.11 and open it in version 4.x, report builder prompts you in Step 2 to update the range by one cell for items that are missing a header.

   ** Change Headers to Excel Auto-Filters:** Available only if row and column headers are displayed. This setting creates an Excel auto filter and appends it to the data report builder returns for this request.

   >[!NOTE]
   >
   >Excel supports only one auto-filter per worksheet. If you create a new auto filter in a worksheet where an auto filter already exists, Excel does not provide a warning that the existing auto-filter is going to be replaced.

   ** Perform Auto-Outline:** Transforms the date returned by report builder from a list view to a tree view.

   ** Name this Request:** Lets you type a user-defined name for the request, or use the default name selected on Step 1. This name appears as the [!UICONTROL Report] name in the [!UICONTROL Request Manager]. See [Name a Request](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D). 

1. Click **[!UICONTROL OK]**.
