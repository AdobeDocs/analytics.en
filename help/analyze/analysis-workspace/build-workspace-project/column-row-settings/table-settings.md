---
description: Row settings vary depending on which component you have dragged into the table.
title: Row settings
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
---

# Row settings

Row settings vary depending on which component you have dragged into the table.

You can also use [right-click actions in a table](/help/analyze/analysis-workspace/visualizations/freeform-table.md) to manage selected row(s).

To access table row settings, click the Settings icon next to a dimension, segment, metric, time period, or a breakdown within each of these:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Row Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > Date Comparisons</a> </p> </td> 
   <td colname="col2"> <p><b>Align dates from each column to all start on the same row. </b> </p> <p>When you choose to align the dates, for example in a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>Disabled by default. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percentages </p> </td> 
   <td colname="col2"> <p><b>Calculate percentages by row</b> </p> <p>Forces the Freeform table to calculate the cell percentages across the row as opposed to down the column. This is especially useful for trending percentages. It is turned on by default when using the <span class="uicontrol"> Visualize</span> icon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Column Totals </p> </td> 
   <td colname="col2"> <p>These settings show up only with <a href="/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md"  > manual (static) rows</a> (when you have selected a finite set of items), not with dynamic rows (when you drop in a dimension that shows all items). <p>Note: For <i>metric</i> manual rows, the setting is disabled, since it doesn't make sense to sum any metrics besides the current rows in a table. </p> </p> <p><b>Calculate Totals by summing the values currently in each column (enabled by default):</b> </p> <p>This option calculates only the rows currently in the table. (Client-side calculation) </p> <p><b>Calculate totals based on all rows for each metric (disabled by default):</b> </p> <p>This option includes all dimension items for this dimension, even those not listed in the table. (Server-side calculation) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breakdowns </p> </td> 
   <td colname="col2"> <p><b>Breakdown by position:</b> </p> <p>You can perform breakdowns based on a fixed location in a Freeform table. For example, you can specify that the top seven rows should always be broken down. </p> <p>(Previously, the list of values in the breakdown were "locked". This led to a situation where, for example, if you broke down <span class="term"> Date</span> by <span class="term"> Page</span>, you got a list of the top 50 pages for your selected date range. If you saved that report and then ran it a month later, the top 50 pages would likely have changed. However, Analysis Workspace would use the results from the original breakdown and return the same pages, but with the current month as the date range.) </p> <p>To perform breakdowns based on a fixed location: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">Break down some of the rows in your table. </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">Click the Settings (gear) icon next to the table row you want in a fixed position. </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">Check the checkbox next to <span class="uicontrol"> Breakdown by position</span>. </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">Change the sort order or the date range and notice that the breakdowns are now tied to the row position, not the hard-coded rows. </li> 
    </ol> <p>Disabled by default. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Row Setting | Description |
|--- |--- |
|Date Comparisons|Align dates from each column to all start on the same row.   When you choose to align the dates, for example in a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1:    Disabled by default.|
|Percentages|Calculate percentages by row  Forces the Freeform table to calculate the cell percentages across the row as opposed to down the column. This is especially useful for trending percentages. It is turned on by default when using the  Visualize icon.|
|Column Totals|These settings show up only with [static) rows](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Show sum of current rows as the total]** - this shows a client-side sum of the rows in the table which means the total will **not** de-duplicate metrics like visits or visitors.</li><li>**[!UICONTROL Show Grand Total]** - this shows a server-side sum, which means the total will de-duplicate metrics like visits or visitors.</li></ul>|
|Breakdowns|Breakdown by position:  You can perform breakdowns based on a fixed location in a Freeform table. For example, you can specify that the top seven rows should always be broken down.  (Previously, the list of values in the breakdown were "locked". This led to a situation where, for example, if you broke down  Date by  Page, you got a list of the top 50 pages for your selected date range. If you saved that report and then ran it a month later, the top 50 pages would likely have changed. However, Analysis Workspace would use the results from the original breakdown and return the same pages, but with the current month as the date range.)  To perform breakdowns based on a fixed location:  
     
     Break down some of the rows in your table.  
     Click the Settings (gear) icon next to the table row you want in a fixed position.  
     Check the checkbox next to  Breakdown by position.  
     Change the sort order or the date range and notice that the breakdowns are now tied to the row position, not the hard-coded rows.  
     Disabled by default.|